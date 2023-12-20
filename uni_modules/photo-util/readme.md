# photo-util
### 开发文档
[UTS 语法](https://uniapp.dcloud.net.cn/tutorial/syntax-uts.html)
[UTS API插件](https://uniapp.dcloud.net.cn/plugin/uts-plugin.html)
[UTS 组件插件](https://uniapp.dcloud.net.cn/plugin/uts-component.html)
[Hello UTS](https://gitcode.net/dcloud/hello-uts)



这是一个相册工具，可以实现获取相册列表，读取相册图片

注意：

1. 使用插件需要打自定义基座
2. 使用前需要申请权限

使用：

```ts
import { Album, albumUtil, mediaFile } from "@/uni_modules/photo-util";
import { uni_XXPermissions } from "@/uni_modules/xx-XXPermissions"

/**
*获取相册列表
*/
getalbums() {
    //相册列表
    const albumArray : Array<Album> = albumUtil.getAlbum()

    const { permission } = albumListLoadData
    if (albumArray.length == 0) {
        // 判断有无权限，xx-XXPermissions是我另一个权限申请的插件，可自行搭配使用
        albumListLoadData.authorizationStatus = uni_XXPermissions.checkSystemPermissionGranted(permission)
    } else {
        //业务代码
    }
}



/**
*获取相册里面的视频和图片
id: 相册id
*/
loadAlbumData(id:number) {
    const value:Array<mediaFile> = albumUtil.getAlbumsData(id)
}




```

