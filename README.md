# LoTUploader

WebUploader基础上的封装改善，一句代码全部实现（样式美化，实例JS优化（配置优化，样式调整，名称+大小显示，错误处理等），后端代码。。。。。）

一句代码：//必填参数：ID，Server地址 （完整案例看Demo部分）
$.lotuploader({lotDocId: 'lot-uploader',lotUrl: '/Home/Upload'});

注意点：

	如果你项目并不使用font-awesome，那请吧.upload-state-done:after样式修改一下，这样成功后就很明了

	案例没有采用纯Net语法，只是把服务端处理用Net处理了下。index.html部分通用
-----------------------------------------------------------------------------------------
#LoTUploader V1.0.2 	
	#单文件自动清空队列

----------------------------------------------------------------------------------------
#基本调用：
	$.lotuploader({lotDocId: 'lot-uploader',lotUrl: '/Home/Upload'});
#调用实例：（单文件上传案例）
	$.lotuploader({
            lotDocId: 'lot-uploader',
            lotUrl: '服务器Post地址',
            oneFile: true,
            fileSize: 1024 * 1024 * 5,
            btnStr: '点我就上传默认展图',
            lotSuccessFunc: function (file,data) {
                //方法主体
            },
            lotErrorFunc: function (msg) {
                $('#lot-uploader').append('<div class="lot-temp" style="color:red">' + msg + '</div> ');
                setTimeout(function () {
                    $('.lot-temp').remove();
                }, 2000);
            }
        });
