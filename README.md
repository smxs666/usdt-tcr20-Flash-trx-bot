# tcr20链上通过usdt兑换trx的telegrambot
本项目采用go语言编写
bug很多仅供参考

注意事项：

请确保在使用之前先替换代码中的 YOUR_ 开头的参数，如 Telegram Bot 的 Token、Webhook URL、SSL 证书路径、监听地址等。
请确保已安装 Go 环境，并使用 go get 安装依赖包：go get github.com/go-redis/redis 和 go get github.com/go-telegram-bot-api/telegram-bot-api。
编译教程：

将上述代码保存到一个名为 main.go 的文件中。
在终端中执行命令 go build -o bot main.go，编译生成名为 bot 的可执行文件。
部署教程：

准备一台服务器，并将生成的 bot 可执行文件上传到服务器上。
根据实际需求，配置服务器的 SSL 证书和 Nginx 反向代理，确保能够通过 HTTPS 访问到 Webhook URL。
在服务器上执行 ./bot 启动程序，此时程序会启动一个 HTTP 服务器，并监听 Webhook 回调。
在 Telegram Bot 管理界面中配置 Webhook，设置 Webhook URL 为服务器上的地址，格式为 https://your-domain.com/your-bot-token，其中 your-domain.com 是服务器的域名，your-bot-token 是 Telegram Bot 的 Token。
部署完成后，就可以通过 Telegram 向 Bot 发送命令，进行 USDT 转账和余额查询了。
