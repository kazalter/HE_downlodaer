# 极简 aria2 引擎：alpine 自带源装 aria2，纯本地起 RPC，启动不联网拉任何东西。
# （换掉 p3terx/aria2-pro：那个每次启动都去 aria2c.vercel.app 拉 trackers/core，
#  国内网络连不上会卡死，RPC 永远起不来。）
FROM alpine:3.20

ARG APK_REPOSITORY=https://mirrors.tuna.tsinghua.edu.cn/alpine
RUN printf '%s/v3.20/main\n%s/v3.20/community\n' "$APK_REPOSITORY" "$APK_REPOSITORY" > /etc/apk/repositories
RUN apk add --no-cache aria2

EXPOSE 6800
ENTRYPOINT ["aria2c"]
