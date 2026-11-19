# Linux：lsof，谁占了我的文件和端口

```bash
lsof -i :8080          # 谁占了 8080 端口
lsof -p 1234           # 进程 1234 打开了哪些文件
lsof /var/log/app.log  # 谁在写这个日志
lsof | grep deleted    # 被删了但还被进程占着的文件（磁盘不释放的元凶）
```

- "端口被占了"先 `ss -tlnp` 看进程，再 `lsof -p` 看它还干了啥。
- 删文件后磁盘不释放：文件被删了但句柄还在，`lsof | grep deleted` 找出来重启进程。
- `lsof` 输出多，配合 `grep` 用，别直接翻。
