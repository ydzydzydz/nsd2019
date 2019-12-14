# nsd1907_devops_day01

## 多进程

- 多进程编程，使用os.fork()创建子进程
- 生成子进程后，后续代码将在父子进程中都执行一遍
- os.fork()的返回值，在父子进程中不一样
  - 父进程中，返回值是非0值（子进程的PID）
  - 子进程中，返回值是0

### 多进程的编程思路

- 父进程只fork子进程
- 子进程做具体的工作
- 子进程工作完成后，exit彻底退出










