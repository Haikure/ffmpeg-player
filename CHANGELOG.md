# FFmpegPlayer 更新日志

## v1.0.2

完整变更：[v1.0.1...v1.0.2](https://github.com/Haikure/ffmpeg-player/compare/v1.0.1...v1.0.2)

### 新增

- 增加按源视频尺寸、显示尺寸和设备像素比计算的自适应视频降采样。
- 增加 OpenGL 多纹理格式的多点采样路径，并保留 CPU 渲染路径的原始帧以支持暂停时重新生成纹理。
- 增加 `VideoPlayer.downsamplingEnabled` 属性，用于在 QML 中控制降采样。

### 修复

- 修复缩放模式继续使用降采样和线性过滤导致画面细节损失的问题；缩放时改用原始采样路径。
- 修复暂停状态切换采样模式后不会刷新当前画面的问题。
- 修复 OpenGL Shader 按采样模式缓存时的材质和 Shader 匹配问题。

### 构建

- 将 FFmpeg 的静态 OpenSSL 依赖固定为 `ffplayer-openssl3 3.5.6`。
