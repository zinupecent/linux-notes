# Linux：文本处理三件套 grep / sed / cut

```bash
grep -rn "TODO" . --exclude-dir=.git   # 递归找内容
grep -c "error" app.log                # 计数

sed 's/old/new/g' file.txt             # 替换（不加 -i 只输出不改文件）
sed -i.bak 's/old/new/g' file.txt      # 原地改，先备份

cut -d: -f1 /etc/passwd                # 按冒号切，取第 1 列
cut -d' ' -f1,3 access.log             # 取第 1、3 列
```

- `grep` 找行，`sed` 改行，`cut` 取列，三个配合能处理大部分文本。
- `sed -i` 不加备份后缀时，改错了找不回来。
