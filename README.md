
# AndroidDevelop
Android开发Demo集合


3.x已经支持java8,所以屏蔽掉了 `lambda` 示例
gradle升级到`3.0`,旧版本的`tinkder`使用的插件过旧，所以也屏蔽掉

> idegen.jar

编译`AOSP`源码生成的jar，如果想把源码导入`AndroidStudio`或者`IDEA`，有了这个jar，就不必需要花费近乎一个小时的时间去重新编译源码，而可以直接导入IDE

请把这个jar包放在 `out` --> `host` --> `darwin-x86` --> `framework`,然后执行`development/tools/idegen/idegen.sh`生成`android.ipr` and `android.imi`,用于导入IDE

如果没有编译过源码是没有 `out` 目录的，请一层一层的新建文件夹，直到新建到`framework`，放进去就OK

`out` 目录与 `.repo` 平级

至于如何编译AOSP源码,请查看这篇Blog ： [Android_编译Android源码并使用AS查看源码](https://7449.github.io/2017/02/10/Android_compile_aosp/)


> cordova-plugin-network

* cordova 插件示例，调用方法：
* 使用时需要自行打印log去测试，java文件中什么都没有做

		<!DOCTYPE html>
		<html>
		<head>
		    <meta charset="utf-8">
		    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
		    <title></title>
		    <meta name="description" content="">
		    <meta name="viewport" content="width=device-width">
		    <link rel="stylesheet" type="text/css" href="css/app.css"/>
		    <script>
				document.addEventListener("deviceready", init, false);
				        function init() {
				            function onSuccess(message) {
				                var options = {
				                    onError: function() {
				                        alert('ERROR');
				                    }
				                };
				            }
				
				            function onFail(message) {
				                alert('Failed because: ' + message);
				            }
				
				            document.querySelector("#network").addEventListener("touchend", function() {
				                navigator.network.start(onSuccess, onFail, {
				                		networkType: Network.NetWorkType.LOGIN,
				                });
				            });
				}
		    </script>
		</head>
		<body>
		<button id="network">插件示例</button>
		
		<script src="cordova.js"></script>
		</body>
		</html>

> scanApp:

![](http://i.imgur.com/bpP2vWA.gif)

> Rvfilter:RecyclerView写的高级筛选

![](https://github.com/7449/AndroidDevelop/blob/master/image/rv_filter.gif)


项目名称					|说明							 |博客地址  																					|单独项目地址
---    					|---   							 |---          																				|---
accessibilityService    |残疾人模式使用					 |无		|无
banner					|首页banner封装					 |[首页banner封装](https://7449.github.io/2016/09/28/Android_AdBannerPackage/)				|[BannerLayout](https://github.com/7449/BannerLayout)
biliRecommendUI			|Bili推荐页面，Toolbar搜索动画 	 |无 																						|无
camera			|试手google开源的[camera](https://github.com/google/cameraview)  |无 														|[Album](https://github.com/7449/Album)
dagger			|试手google开源的[dagger](https://github.com/google/dagger)  |无 														|无
expandableList	|类似功能：qq好友分组 				 |[Adnroid_expandablelist](https://7449.github.io/2017/01/01/Adnroid_expandablelist/) 																						|无
finger				|指纹识别的Demo					 |[指纹识别测试](https://7449.github.io/2016/11/28/Android_finger/) 									|无
fuckApp					|通过root权限彻底隐藏系统垃圾应用 	 |[通过root权限彻底隐藏系统垃圾应用](https://7449.github.io/2017/01/03/Android_hideApp/) 																						|无
greenDao				|greenDao2.X版本使用示例 			 |[greenDao增删改查](https://7449.github.io/2016/10/08/Android_greenDaoCRUD/) 						|无
greendao_3.0			|greenDao3.X版本使用示例 			 |[greenDao增删改查](https://7449.github.io/2016/10/08/Android_greenDaoCRUD/) 						|[ZLSimple](https://github.com/7449/ZLSimple)
greenDaoExternal     	|利用greenDao操作第三方数据表 		 |[greenDao增删改查](https://7449.github.io/2016/10/08/Android_greenDaoCRUD/) 						|无
greenDaoMultiTable     	|greenDao多表关联		 |[greenDao增删改查](https://7449.github.io/2016/10/08/Android_greenDaoCRUD/) 						|无
imageSelect     	|简单的图片选择器		 |无 						|[Album](https://github.com/7449/Album)
jsTest     	|js与android互调		 |无 						|无
lazyFragment   			|Fragmentviewpager使用时懒加载   	 |[Fragment懒加载](https://7449.github.io/2016/10/15/Android_LazyFragment/) 								|[Retrofit_RxJava_MVP](https://github.com/7449/Retrofit_RxJava_MVP)
refreshLayout 			|Demo修改自[Yalantis/Phoenix](https://github.com/Yalantis/Phoenix) |无 												|无
linkTop 			|CoordinatorLayout的一种使用方法 |无 												|无
numberPickerView 			|选择器 |无 												|无
objectBox 			|ObjectBox数据库 |[Android_objectBox](https://7449.github.io/2017/09/28/Android_objectBox/)												|无
objectBoxMultiTable 			| ObjectBox数据库多表关联 |[Android_objectBox](https://7449.github.io/2017/09/28/Android_objectBox/)												|无
saveImage				|保存图片在本地 					 |[ImageView保存本地](https://7449.github.io/2016/11/21/Android_SaveImageView/) 						|无
superAdapter			|RecyclerViewBaseAdapter		 |无 																						|[XAdapter](https://github.com/7449/XAdapter)
tabFragment				|FragmeLayout切换Fragment   		 |[FragmeLayout切换不同的Fragment](https://7449.github.io/2016/10/05/Android_TabFragment/) |无
tinker				|Tinker的一个小Demo   			 |[Tinker初次试用](https://7449.github.io/2016/11/04/Android_tinker/) 							|无
viewPagerFragment 		|ViewPagerFragment滑动带有光标	 |[ViewPager+Fragment滑动且带有光标](https://7449.github.io/2016/10/05/Android_ViewPager_Fragment/) |无
wheelView 		|省市县三级联动  					 |[省市县三级联动](https://7449.github.io/2016/10/26/Android_Citylinkage/) 								|无
slideView				|联系人侧栏快速索引 				 |[SlideView](https://7449.github.io/2016/10/07/Android_SlideView/) |[SlideView](https://github.com/7449/SlideView)
downloadProgressBar  	|下载进度展示 					 |[DownloadProgressBar](https://7449.github.io/2016/10/07/Android_DownloadProgressBar/) |[ProgressView](https://github.com/7449/ProgressView)
fractionView			|自定义view两个相反方向的嵌套转盘    |[FractionView](https://7449.github.io/2016/10/26/Android_FractionView/) |[FractionView](https://github.com/7449/FractionView)
bannerLayout			|最简单方式实现Banner				 |[BannerLayout](https://7449.github.io/2016/10/26/Android_BannerLayout/)  			|[BannerLayout](https://github.com/7449/BannerLayout)
lambda			|Android中使用Lambda				 |[Android_Lambda](https://7449.github.io/2017/02/08/Android_Lambda/)  			|[ZLSimple](https://github.com/7449/ZLSimple)
shortcuts			|7.0新特性小图标			 |无  			|无
statusBarTest			|高版本状态栏适配测试			 |[Android_statusbar](https://7449.github.io/2017/05/15/Android_statusbar/)  			|无