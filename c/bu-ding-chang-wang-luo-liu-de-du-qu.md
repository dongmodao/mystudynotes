# 不定长网络流的读取

重点是在于设置 ``stream.ReadTimeout`` 属性，如果不设置，这个时间会很长，程序会一直在等待数据的读取，而造成迟迟得不到结果。

代码的分析暂时就不进行了，这是我在网页上找了很多版本中的一个的个人修改版，否则还是会在 ``ReadTimeout`` 上出现问题。主要代码如下：

``` csharp
        /// <summary>
        /// 读取不定长的流进入字节数组
        /// </summary>
        /// <param name="stream"></param>
        /// <param name="BufferLen"></param>
        /// <returns></returns>
        private static byte[] Read2Buffer(Stream stream, int BufferLen)
        {
            // 如果指定的无效长度的缓冲区，则指定一个默认的长度作为缓存大小
            if (BufferLen < 1)
            {
                BufferLen = 0x8000;
            }

            // 初始化一个缓存区
            byte[] buffer = new byte[BufferLen];
            int read = 0;
            int block;
            stream.ReadTimeout = 300;
            try
            {
                // 每次从流中读取缓存大小的数据，直到读取完所有的流为止
                while ((block = stream.Read(buffer, read, buffer.Length - read)) > 0)
                {
                    // 重新设定读取位置
                    read += block;

                    // 检查是否到达了缓存的边界，检查是否还有可以读取的信息
                    if (read == buffer.Length)
                    {
                        // 尝试读取一个字节
                        int nextByte = stream.ReadByte();

                        // 读取失败则说明读取完成可以返回结果
                        if (nextByte == -1)
                        {
                            return buffer;
                        }

                        // 调整数组大小准备继续读取
                        byte[] newBuf = new byte[buffer.Length * 2];
                        Array.Copy(buffer, newBuf, buffer.Length);
                        newBuf[read] = (byte)nextByte;

                        // buffer是一个引用（指针），这里意在重新设定buffer指针指向一个更大的内存
                        buffer = newBuf;
                        read++;
                    }
                }
            }
            catch (Exception)
            {

            }
            // 如果缓存太大则使用ret来收缩前面while读取的buffer，然后直接返回
            byte[] ret = new byte[read];
            Array.Copy(buffer, ret, read);
            return ret;
        }
```

这个代码的最初版本的原出处我忘记记录了，如果有人发现，可以给我留言，我会补上引用。代码的说明会在过段时间补上来。

