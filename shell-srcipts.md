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

函数是实现一系列操作的代码块。

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

## 比较

| 类型 | |
| :---: | :---: |
| -eq | 相等 |
| -gt | 大于 |
| `[[ string1 == sting2 ]]` 或 `[ "string1" = "string2" ]` | 字符串比较 |
| `[[ string1 > string2 ]]` | 字符串排序 |
| `strlen=${string}` | 字符串长度 |

## 检测

存在性检测: -f（文件是否存在），-d（目录是否存在）

## 结构

### 条件结构

if：进行条件选择

```shell
if [ condition ] ; then
  Statements
elif [ condition ] ; then
  Statements
else
  Statements
fi
```

case ：用于匹配多个情况，易读性易用性强

```shell
case expression in
  pattern1) execute commands;;
  pattern2) execute commands;;
  pattern3) execute commands;;
  pattern4) execute commands;;
  *)        execute some default commands or nothing ;;
esac
```

### 循环结构

for循环：变量循环次数

```shell
for var in list
do
  statements
done
```

```shell
while condition
do
  Statements
done
```

```shell
until condition
do
  Statements
done
```

## 算术表达式（Arithmetic Expressions）

多种方法：
- expr工具：numA op numB
- $((...))
- let工具：let expression
- var=$((...))

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

# Debug

```shell
bash -x ./script_file
```

# 常见 shell

sh, csh, tcsh, ksh, bash
