# Linux：文件操作 cp / mv / rm / ln

```bash
cp file.txt /tmp/          # 复制
cp -r dir/ /tmp/           # 复制目录要加 -r
mv old.txt new.txt         # 重命名 / 移动
rm file.txt                # 删除（没有回收站）
rm -rf dir/                # 递归强制删，慎用
ln -s /real/path link      # 软链接
ln /real/path link         # 硬链接
```

- `rm -rf` 之前先 `ls` 确认路径，别用变量拼路径时手滑。
- 软链接存的是路径，目标删了就成断链；硬链接和原文件共享 inode。
- 复制时保留权限和时间用 `cp -a`。
