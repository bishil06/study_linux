# Study Linux
리눅스에 대해 공부한 내용을 작성하는 저장소입니다.
  
## Command standard heading
stdin, stdout, -file, --opt, --help, --version  
ex) ls [options] [*files*]  
* [ options ]   
입력할 필요가 없고 선택적으로 입력이 가능하다  
``` shell
bash-3.2$ ls
README.md
```
* italic체  
실제 파일명과 같이 스스로 선택한 특수한 값을 입력
``` shell
bash-3.2$ wc README.md 
       4      12      89 README.md
bash-3.2$ wc README.md *.md
      41     152     960 README.md
      41     152     960 README.md
      82     304    1920 total
```
* ( file | directory )  
둘중하나를 선택적으로 인자로 넣을 수 있다  
``` shell
bash-3.2$ touch test
bash-3.2$ mkdir test_dir
bash-3.2$ mv test test2
bash-3.2$ mv test_dir test_dir2
bash-3.2$ ls
README.md       test2           test_dir2
```
* stdin  
키보드와 같은 표준 입력
* stdout  
모니터와 같은 표준 출력
* file  
입력파일명 대신 '-' 가 있다면 표준입력으로부터 값을 받음, 출력 파일명 자리에 있다면 표준 출력으로 값을 출력함
``` shell
bash-3.2$ cat -
hi
hi
hello
hello
^C
```
* -- opt  
명령행 옵션에 -- 기호를 삽입하면 이는 옵션의 마지막을 의미함, 그 이후의 것은 옵션으로 취급되지 않음
``` shell
bash-3.2$ ls -l
total 16
-rw-r--r--  1 superlee  staff    3  2 13 01:51 -
-rw-r--r--  1 superlee  staff  960  2 13 01:55 README.md
bash-3.2$ ls -- -l
ls: -l: No such file or directory
bash-3.2$ ls -l --
total 16
-rw-r--r--  1 superlee  staff    3  2 13 01:51 -
-rw-r--r--  1 superlee  staff  960  2 13 01:55 README.md
```
* -- help  
명령어의 적절한 사용법 출력
``` shell
 git --help                                                                                                                                                           
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index
...
```
* -- version  
해당 명령어의 버전 정보
```shell
git --version                                                                                                                                                         
git version 2.24.3 (Apple Git-128)
```