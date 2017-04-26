RecyclerView 在加载网页图片有时候会发生一些错乱的情况。形成这个情况的原因是 RecyclerView 对列表的元素进行的重用。即完全移出了屏幕的 Items 将很快被重新使用，通常是加到末尾，即使你设置了缓存，但是超过了这个部分还是会被重用的，而被重用的 Items 可能此时就会响应到请求的图片，特别是在一些比较耗时的请求时出现。

针对这种情况，目前看到的有以下几种解决方案。

1. 使用 RecyclerView 的 setIsRecyclable(false) 方法，设定不重用 Items，当然这会造成加载更加缓慢一些，不过影响一般不大。适用于总的 Items 数目不是太大的情况下，否则将很烧内存。

2. 在 Adapter 中的 onBindViewHolder() 加载图片前，先清理旧的图片
``` java
imageView.setImageDrawable (null);
//或者如下
/**
*Cancel any pending loads Glide may have for the view and free any resources that may have been loaded for the view.
Note that this will only work if View.setTag(Object) is not called on this view outside of Glide.
*/
Glide.clear(holder.imageView);
```
3. 我认为上述方法都不是最优的解决方式，等待补充。