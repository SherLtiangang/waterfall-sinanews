# waterfall-sinanews
[预览地址](https://sherltiangang.github.io/waterfall-sinanews/index.html)

## 懒加载原理
懒加载实际就是将页面上所有的图片都换成一个相同的路径，当用户滚动看到图片时，再将路径换成图片的原路径。
我们假设一个有页面，页面上存在有很多的图片。当用户加载这个页面的时候，会展示出当前视窗的图片，而用户看不到的图片，则用相同的图片去替代。用户如果滚动不到之后的图片，将不会被加载出来，而当用户滚动之后，后面的图片会改成真实的图片去展示。

## 瀑布流原理
瀑布流的元素是等宽从上到下依次排列的，需要给元素设定绝对定位，通过调节`top`和`left`的来改变元素的位置。定义一个空数组，数组内元素的个数就是瀑布流的列数，元素的值就是高度。将数组内的每个元素的初始值都设为0，然后向里面去放置图片，增加高度。由于图片是放置在所有列中最低的一列下的，因此需要做判断。当高度最小时，放置图片，增加当前列的高度，以此类推。

## 实现原理
获取10条数据，把10条数据拼装成`dom`放到页面上，使用瀑布流去摆放`dom`的位置,在`html`最后添加一个`load`元素，当`load`元素出现在页面上时，获取之后的10条数据，依次类推......
