# Shell 脚本（Shell Scripting）

- 复用（减少错误、组合工具、无需编译）
- 执行（编译应用、内置shell脚本、其他语言脚本）

# 语法（Syntax）

## 注释（Comment）

```shell
# Comment
```

## 命令解释器指定（Command Interpreter）

```shell
#!/path/to/CommandInterpreter
```

## 变量（Variables）

```shell
# 变量引用，于变量名加美元符号
$var
```

## 函数（Functions）

```shell
# 函数声明（Function Declaration）
fun() {
  statements
}

# 函数调用（Function Calling）
fun
```

## 输入/输出（Input/Output）

```shell
# 利用 echo 输出信息
echo "Message"
# 利用 read 读取输入
read
```

**命令串接（Chaining Commands）**

命令串接方式：
- `;`：无论前命令是否成功执行，后命令定然可执行
- `&&`：后续命令受前命令影响
- `||`：逐一执行直到命令成功

对比 pipe，pipe 在后续命令开始前退出当前命令

## 脚本参数（Script Parameters)

在命令行执行脚本时，可以传入参数，如

```shell
$ ./script.sh argument1 argument2 ...
```

在 shell脚本中，可以利用特殊字符引用相应参数

| 特殊字符 | 意义 |
| :---: | :---: |
| `$0` | 脚本名 |
| `$1`，`$2`，... | 第n个参数 |
| `$*` | 所有参数 |
| `$#` | 参数的个数 |

## 命令替换（Command Substitute）

将某命令结果作为另一命令的一部分

```shell
# 建议使用
cat $(ls)

# 不建议使用
cat `ls`
```

## 内置命令查询

在 shell prompt 处输入 `help` 即可

# 常见 shell

sh, csh, tcsh, ksh, bash
