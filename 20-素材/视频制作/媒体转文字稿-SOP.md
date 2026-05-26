# 媒体转文字稿 SOP

## 什么时候用

当用户给出一个本地视频或音频，并且目标是“拿到文字稿”时，默认走这套。

## 默认约定

1. 默认只产出 `transcripts/<媒体文件名>/文字稿.md`。
2. 视频和音频统一处理，`录音/` 下的 `.m4a` 也直接走同一个入口。
3. 文字稿写入来源文件、源文件修改时间、时长和转写方式。
4. 默认走豆包语音识别，尽量不把长转写塞进聊天上下文。
5. 默认不额外生成字幕、原始 JSON 和中间音频；需要校对时再加参数。

## 执行入口

第一次在新 Mac 上准备环境：

```bash
ops/media-transcript/bootstrap_macos.sh
```

日常转写：

```bash
python3 ops/media-transcript/transcribe_media.py \
  "/path/to/media"
```

## 迁移备注

My brain 迁移到新电脑时，把仓库带过去即可。这个能力依赖本机的 `python3`、`ffmpeg` 和豆包语音 API Key；把 `ops/media-transcript/.env.local.example` 复制成 `.env.local` 并填好 key，再跑初始化命令。

默认开启识别侧标点；需要更高可读性时，再对某一份文字稿单独整理。
