![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/ZLPhotoBrowser.png)

[![Version](https://img.shields.io/cocoapods/v/ZLPhotoBrowser.svg?style=flat)](http://cocoadocs.org/docsets/ZLPhotoBrowser)
[![License](https://img.shields.io/cocoapods/l/ZLPhotoBrowser.svg?style=flat)](http://cocoadocs.org/docsets/ZLPhotoBrowser)
[![Platform](https://img.shields.io/cocoapods/p/ZLPhotoBrowser.svg?style=flat)](http://cocoadocs.org/docsets/ZLPhotoBrowser)
![Language](https://img.shields.io/badge/Language-%20Objective%20C%20-blue.svg)

----------------------------------------

### 框架整体介绍
* 该框架为一个多选照片（支持多选视频、gif、Live Photo）的框架，兼容设备开启的iCloud照片存储，支持编辑裁剪图片，支持记录历史选择照片。
* [功能介绍](#功能介绍)
* [更新日志](#更新日志)
* [使用方法(支持cocoapods安装)](#使用方法)
* [效果图](#效果图)

### <a id="功能介绍"></a>功能介绍
- [x] 支持横竖屏
- [x] 预览快速选择、可设置预览最大数
- [x] 直接进入相册选择
- [x] 查看、选择gif、LivePhoto(iOS9.0)、video
- [x] 3D Touch预览image、gif、LivePhoto、video
- [x] 混合选择image、gif、livePhoto、video
- [x] 控制选择video最大时长
- [x] 裁剪图片(可自定义裁剪比例)
- [x] 多语言国际化(中文简/繁、英文、日文)
- [x] 相册内拍照按钮实时显示镜头捕捉画面
- [x] 预览已选择照片
- [x] 自定义圆角弧度
- [x] 自定义升序降序排列
- [x] 多张拍照
 
### 更新日志
```
● 2.3.2: 新增设置导航颜色api，初步适配横屏，适配iPad;
● 2.2.9: 新增单选模式下选择图片后直接进入编辑界面功能，提供设置裁剪比例api;
● 2.2.8: 更新编辑图片功能，增加裁剪比例选项(1:1, 3:4, 2:3, 9:16,等比例，开发者可根据需求，按照规则自行添加所需比例);
● 2.2.6: ①：可混合选择image、gif、livephoto、video类型;
         ②：支持video、gif、livephoto类型的多选;
         ③：支持控制video最大选择时长;
● 2.2.3: 新增图片编辑功能;
● 2.2.1: 新增3D Touch预览功能 (需设备支持);
● 2.2.0: 优化内存问题;
● 2.1.9: 新增选择及预览Live Photo功能 (iOS 9.0);
● 2.1.7: 新增内部拍照按钮实时显示相机俘获画面功能;
● ... 新增gif及video选择功能;
```

### 框架支持
最低支持：iOS8.0

### <a id="使用方法"></a>使用方法

第一步：
* Manually 
  * 1.直接把PhotoBrowser文件夹拖入到您的工程中
  * 2.导入 Photos.framework及PhotosUI.framework
  * 3.导入 "ZLPhotoActionSheet.h"
* Cocoapods
  * 1.在Podfile 中添加 `pod 'ZLPhotoBrowser'`
  * 2.执行 `pod install` 或 `pod update`
  * 3.导入 \<ZLPhotoActionSheet.h\>

第二步：
- 在项目plist配置文件中添加如下键，值并设为YES
```objc
Localized resources can be mixed YES
//或者右键plist文件Open As->Source Code 添加
<key>CFBundleAllowMixedLocalizations</key>
<true/>
```

代码中调用
```objc
#import "ZLPhotoActionSheet.h"
    
ZLPhotoActionSheet *actionSheet = [[ZLPhotoActionSheet alloc] init];
//设置照片最大预览数
actionSheet.maxPreviewCount = 20;
//设置照片最大选择数
actionSheet.maxSelectCount = 10;
actionSheet.sender = self;

[actionSheet setSelectImageBlock:^(NSArray<UIImage *> * _Nonnull images, NSArray<PHAsset *> * _Nonnull assets, BOOL isOriginal) {
    //your codes
}];

[actionSheet showPreviewAnimated:YES];
```

### <a id="效果图"></a> 效果图
- 多语言国际化效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/english.png)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/japan.png)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/zh-hans.png)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/zh-hant.png)

- 3DTouch预览效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/forceTouch.gif)

- 编辑功能预览图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/edit.gif)

- 混合选择预览图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/mixSelect.gif)

- 横屏预览图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/landscape.gif)

- 预览快速多选效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览图快速选择.gif)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览大图快速选择.gif)

- 直接进入相册选择相片效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/直接进入相册选择相片.gif)

- 预览大图及缩放效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/查看大图支持缩放.gif)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览选择gif.gif)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览选择视频.gif)

- 拍照
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/相册内部拍照.gif)

- 相册内混合选择效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/相册内混合选择.gif)

- 预览已选择照片效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览已选择照片.gif)
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/预览确定选择的照片.gif)

- 原图功能效果图
![image](https://github.com/longitachi/ZLPhotoBrowser/blob/master/效果图/原图功能.gif)

