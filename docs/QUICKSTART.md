# 简短准备清单

按要使用的阶段准备即可。JSON 中保留模型选择与生成参数；输入素材和输出名称已改为通用示例。

| 阶段 | 模型 | 准备说明 |
| --- | --- | --- |
| 出图 | Qwen-Image 2.1 | [ComfyUI 模型包](https://huggingface.co/Comfy-Org/Qwen-Image-2.1)，配套文本编码器与 VAE |
| 视频 | Wan2.2 I2V A14B | [ComfyUI 模型包](https://huggingface.co/Comfy-Org/Wan_2.2_ComfyUI_Repackaged)，高/低噪声模型、文本编码器与 VAE |
| 音效 | MMAudio Large 44k v2 | [节点与准备说明](https://github.com/kijai/ComfyUI-MMAudio)，配套 VAE、Synchformer、CLIP 与 BigVGAN |
| 音效 | HunyuanVideo-Foley XXL | [节点与准备说明](https://github.com/if-ai/ComfyUI_HunyuanVideoFoley)，按节点仓库准备配套权重 |

视频读取与导出使用 [VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite)。图片与帧处理的辅助节点使用 [ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes)。如工作流提示缺少节点，按实际缺失项安装后重启 ComfyUI。

## 图片与视频输入

- 出图工作流：上传自己的参考图，修改画面提示词。
- 首尾帧工作流：上传 `first_frame.png` 和 `last_frame.png`，也可直接在节点中选择其他文件。
- 图生视频工作流：上传起始画面 `first_frame.png`。
- 视频配声工作流：上传剪辑完成的视频 `video.mp4`。
- 分层混音工作流：上传已有底声的视频 `video_with_audio.mp4`，按自己的镜头修改画面截取和音效起始位置。

先在两种视频配声方案中任选一种试听；两者也可以搭配使用。分层示例是针对武侠场景的编辑模板，重点声音的同步与音量需要试听调整。

显卡分工由自己的启动方式设置；工作流 JSON 不负责分配显卡。视频和音效可以依次运行在同一张卡上。
