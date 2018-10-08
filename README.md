# pdb_debuging_techniques

GDB调试core文件详解 (https://blog.csdn.net/u010889616/article/details/48815321)

假如coremain.cpp是产生segmentation fault的文件，可以按照下列步骤找出bug所在的行号：
1. g++ coremain.cpp -g -o coremain # 需要使用-g 选项
2. ./coremain
3. 找到core文件的path，假如它为core.coremain：如果文件没有使用chdir函数，它应该在coremain.cpp所处的位置；否则，看看chdir目标位置
4. gdb core.coremain # 可以查看core.coremain的文件内容，查看函数调用的栈，找出问题的行号。
