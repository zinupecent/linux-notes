# Linux：awk，按列处理文本

```bash
# 打印第 1 列和第 3 列
awk '{print $1, $3}' access.log

# 按冒号切分，打印用户名
awk -F: '{print $1}' /etc/passwd

# 条件过滤：第三列大于 100 的行
awk '$3 > 100' data.txt

# 统计：求和
awk '{sum += $2} END {print sum}' nums.txt

# 内置变量：NR 行号，NF 列数
awk '{print NR, $0}' file.txt
```

- `awk` 是"按列"处理，`grep` 是"按行"找，`sed` 是"按行"改。
- `$1` 第一列，`$0` 整行，`NF` 是列数，`NR` 是行号。
- 简单的列提取用 `cut -d' ' -f1` 也行，复杂条件再上 awk。
