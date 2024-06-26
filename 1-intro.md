# Introduction to Linux OS and basics of Bash programming


### Linux Terminal (Լինուքսի հրամանների տողը)

> Ներածական հարցեր թեմայի վերաբերյալ 

* Ծանո՞թ եք տերմինալի միջոցով Linux-ում աշխատելուն
* Եթե այո ի՞նչ ծրագրի միջոցով
* Ծանո՞թ եք SSH-ով միանալուն
  * Putty
  * Xshell
  * MobaXterm
* Ծանո՞թ եք Windows Subsystem for Linux (WSL) in Windows 10/11
  

Լինուքս համակարգ մուտքագրվելու հիմնական ձևն է՝
անուն (username) և գաղտնաբառ (password) մուտքագրելը

SSH-ով միանալու պարագայում գաղտնաբառի փոխարեն հնարավոր է մուտքը զույգ-բանալիներով (Public/Private Keys)

Մուտքագրվելիս Լինուքս համակարգ հնարավոր է աշխատել հետևյալ տարբերակներից մեկով. 
* Graphical User Interface (GUI)
* Command Line Interface (CLI) / Terminal

Այս դասընթացի ընթացքում մենք կաշխատենք երկրորդ տարբերակով:

<br><br>

### Linux VM remote access

* **Oracle VM VirtualBox** միջավայրում միացրեք **Ubuntu-22.04** վիրտուալ մեքենան


* Մուտքագրվեք `student` անունով և նկատեք ՝IPv4 address`-ը:


* Միացեք SSH-ով տվյալ անունով ու հասցեյով:


### Linux Terminal, CLI Basics

> Ինչ է Terminal-ը

Ծրագիր, որի ներսում գոծում է հրամանի տող (Command Line): 
Հնարավոր է դա լինի հեռակա միացումով (remote connection/access):
Այսինքն աշխատանքը իրականացվի ցանցով կապված մեկ այլ հեռակա համակարգի վրա:

> Ինչ է Command Line Interface/Interpreter (CLI) / Shell 

Ծրագիր, որը իրականացնում է հրամանի տողի աշխատանքը, 
վերլուծում է (interpret) տողը ու կատարում հրամանը կամ հայտնում սխալի մասին:

Հրամանները վերլուծվում են տող առ տող, այդ պատճառով ամեն մի հրամանը պետք է ավարտվի **[Enter]**-ով:
** [Enter]**-ից հետո հրամանը այլևս հնարավոր չէ փոխել:

> **#**  նշանը և դրանից հետո ամեն ինչը համարվում է comment և չի վերլուծվում:  

CLI այլ կերպ նաև անվանվում է Shell: Լինում են տարբեր տեսակներ, ամենատարածվածը` **Bash**

CLI / Shell / Bash աշխատում է ինտերակտիվ եղանակով, որը նաև անվանում են REPL 


**Read** -> **Evaluate** -> **Print** -> **Loop**  



> Լինուքսի յուրահատկությունը

Մեծատառի/փոքրատառի տարբերություն (LiNuX iS CaSe SeNsItIvE)

  * Հրամանների և ծրագրերի անվանման մեջ 
    * `command`
    * `Command` 
    * `COMMAND` 
    
  * Ֆայլերի և դիրեկտորիաների/ֆոլդերների անվանման մեջ
    * `file`
    * `File`
    * `FILE`
    
  * Օգտագործողների և խմբերի անվանման մեջ
    * `user`
    * `User`
    * `USER`


> Command Prompt

Տողային հարաման մուտքագրելու հրավեր:

Օրինակներ.

**$** - User Prompt

**#** - ROOT Prompt

Այս հրավերի տեսքը հնարավոր է փոխել, 
սակայն հաճախ նշված նշանները պահպանվում են 
և ավելանում է լրացուցիչ տեղեկություն, 
օրինակ՝ սերվերի, օգտագործողի, տվյալ դիրեկտորիայի անունները:

`student@server:/usr/bin$`

<br><br>

> Movement in command line

Աջ/ձախ սլաքներից բացի հրամանային տողում տեղաշարժ

* `Ctrl-A` – տեղափոխել տողի սկիզբ
* `Ctrl-E` – տեղափոխել տողի վերջ


> Command structure

Հրամանների կառուցվածք

<img src=https://github.com/trainart/introlinuxshell/blob/main/img/command-structure.png width=50% height=50% >

> Հրամանների օրինակներ


* echo - display a line of text 
```bash
echo We learn Linux # this is a comment 
```
```bash
# echo We learn Linux # this is a comment
```

```bash
echo "$USER" learns Shell Programming
```
```bash
echo My Shell is: "$SHELL"
```

* sleep - delay for a specified time 

```bash
echo ; echo -n "Be patient " ; sleep 2 ; echo -n "to learn " ; sleep 2 ; echo "Shell Programming in Linux" ; sleep 2 ; echo 

```

* id - display user information

```bash
id
```

```bash
id --help
```

```bash
id -u
```

```bash
id -u -n
```

```bash
id -un
```


* date - display date

```bash
date
```

```bash
date --help
```

> Use `Shift-PgUp` to scroll up 

```bash
date +"%d-%m-%Y"
```

> Command History 

Նախորդ հրամանները հիշվում են, որ նորից նույնը չհավաքենք:

* Վերևի սլաքը (Up Arrow) նախորդ հրամանները
* Որոնում նախորդ հրամաններում `Ctrl-R`
  * մուտքագրեք հրամանի սկիզբը
  * Կրկնելով `Ctrl-R` հնարավոր է փնտրել նախորդ տարբերակները
    * Օրինակ՝ սեղմեք `Ctrl-R` և հավաքեք ՝da`
    * Կրկնեք `Ctrl-R`
  

> Filename/Command completion 	

Հնարավոր է ամբողջությամբ չլրացնել հրամանի/ֆայլի անունը՝ համակարգը կարող է ամբողջացնել անունը

* `[Tab]`	հրամանի/ֆայլի լրացում, եթե դա միակ տարբերակն է
  * Օրինակ՝ հավաքեք ՝sle` և `[Tab]`

<br><br>
* `[Tab] [Tab]` եթե մեկից ավել տարբերակ կա, ապա ցուցադրվում են բոլոր տարբերակները
  * Օրինակ՝ հավաքեք ՝sl` և `[Tab] [Tab]`

<br><br>

### File Management Commands

> Ֆայլերի անվանումը
* Windows
  * `C:\Program Files\Oracle\VirtualBox\VirtualBox.exe`

* Linux/UNIX

  * `/home/user1/docs/letter.txt`
  * `/bin/ls`


#### Ծանոթացում ֆայլային համակարգի կառուցվածքին

```bash 
ls /
```

```bash
man file-hierarchy
```

> Ավելին իմանալու համար. https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard 



Երբ մուտքագրվում եք  (բացվում է Terminal-ը), հայտնվում եք ֆայլային համակարգի ընթացիկ դիրեկտորիայում:

> Հիմնական հրամաններ
* `pwd` - ընթացիկ դիրեկտորիան
* `cd` - փոխել ընթացիկ դիրեկտորիան
  * Օրինակ՝ հավաքեք ՝cd /h` և `[Tab]` հետո ևս մեկ `[Tab]`
  * Օրինակ՝ հավաքեք ՝cd /u` և `[Tab]` հետո `lo` և `[Tab]` հետո `b` և `[Tab]`


* `ls` - ֆայլերի ցուցակ
<hr>

`ls [options] <directory/file>`

* `-l`  ընդլայնված ցուցակ
* `-a`  ցույց տալ բոլոր ֆալերը  (նեռարյալ .-ով սկսվող ֆալերը )
* `-S`  դասավորել ֆայլերը ըստ չափի (–lS)
* `-r`  Հակադարձ դասավորման կարգով (–lSr)
* `-h`  Մարդու համար ավելի ընթեռնելի (ֆայլերի չափը k, M, G-ով)


<hr> 

> ՕԳՏԱԿԱՐ ԿԱՅՔ՝ 
> https://explainshell.com/
> հրամանների մանրամասն բացատրություն: 
> Բացեք կայքը և մուտքագրեք հրաման, օրինակ

```bash
id -u -n
```

կամ

```bash
echo -n "Be patient " ; sleep 2 ; echo -n "to learn"
```
<hr> 

> Հատուկ անվանումներ
* `/`   Գլխավոր դիրեկտորիան
* `.`    Տվյալ դիրեկտորիան
* `..`   Նախորդ (վերևի) դիրեկտորիան
* `~`    Օգտագործողի անձնական դիրեկտորիան
* `.`-ով սկսվող ֆայլերը սովորաբար օգտագործվում են անհատական կարգավորումները պահելու համար:
  (կետը տվյալ դեպքում ֆայլի անվանման մասն է)


Օրինակներ՝

`./a`        նույնն է ինչ   `a`

`../home/student`  մեկ մակարդակ վերև և home/student

```bash
ls -la ~/.bash*
```


<hr>

> Հիմնական հրամաններ
* `touch`                    Ստեղծել դատարկ ֆայլ
* `cp <fromfile> <tofile>`   	Պատճենել ֆայլը
* `mv <fromfile> <tofile>`	Տեղափոխել / վերանվանել ֆայլը
* `rm <file>`  			Հեռացնել ֆայլ/դիրեկտորիա
* `mkdir <newdir>`		 Ստեղծել դիրեկտորիա 
* `alias <alias> <command>` Ստեղծել հրամանի կրճատում 


> Հրամանների օրինակներ

```bash 
cd /home ; pwd ; ls -la
```

```bash 
cd ; ls -la /home
```

```bash 
mkdir d1 ; cd d1 ; pwd ; touch f1 ; ls f*
```

```bash 
cp f1 f2 ; ls f*
```

```bash 
mv f2 f3 ; ls f*
```

```bash 
alias del="rm -i" ;\
alias

```

```bash
echo 'alias del="rm -i"' >> ~/.bash_aliases

```


```bash 
del f*
```

```bash 
cd ~ ; rm -r d1
```


<hr>

```bash 
cp -r /etc ~
```

```bash 
mkdir ~/TEST
```

```bash 
mv  ~/etc  ~/TEST
```

```bash 
rm -r ~/TEST
```


#### PRACTICE

* `clear` հրամանը մաքրում է էկրանը
  * ստեղծել `c` անունով `alias`, որ մաքրում է էկրանը
  * պահպանել այն, որ գործի մյուս մուտքագրվելիս նույնպես

* ստեղծել երկու հրամանից բաղկացած `alias`, որը
  * կտեղափոխի վերեվի դիրեկտորիա 
  * և պտպի ներկայիս գտնվելու վայրը 
  * պահպանել այն, որ գործի մյուս մուտքագրվելիս նույնպես


### Փոփոխականներ
Shell/Bash variables - temporary storage for information
Bash does not care about the type of variables. 
Variables could store strings, characters or integers. 

Variable names are uppercase by convention, but lowercase and other symbols can be used as well.

Syntax: **VARNAME=VALUE**

> Note: There should be no space around `=` sign 

The example assigns the value `/usr/bin` to the variable called `LIST`
Prefix the variable name with `$`, which will give the value stored in that variable.

#### PRACTICE

```bash
LIST="/usr/bin/" ; ls -l $LIST
```


<br><br>

## Access files

There are several tool to view text files contents.

> **less** - view/browse text file page-by-page

* **Enter/DOWNARROW**	– մեկ տող ներքև
* **SPACE/PgDn**		– մեկ էկրան ներքև
* **PgUp/b**			– մեկ էկրան վերև
* **UPARROW**			– մեկ տող վերև
* **/**					– որոնում
* **Home**				– անցնել տեքստի սկիզբը
* **End**				– անցնել տեքստի վերջը
* **q**					– ելք

> Օրինակներ
 
```bash
less /etc/services
```

```bash
ls /usr/bin | sort -r | less
```


<br><br>

> **cat** - output whole file to STDOUT (default - terminal)

> Օրինակներ
 
```bash
cat /etc/services
```

```bash
cat /etc/services | sort -r
```

```bash
cat /etc/services | sort -r | less
```

Create file `~/newfile`
(end with `Ctrl-D`)

```bash
cat > ~/newfile
```

Check what's inside

```bash
cat ~/newfile
```


Add text to the file `~/newfile`
(end with `Ctrl-D`)

```bash
cat >> ~/newfile
```

Again check what's inside

```bash
cat ~/newfile
```


<br><br>

> **head** - output some first lines (default 10) of file STDOUT (default - terminal)

> Օրինակներ
 
```bash
head /etc/services
```

```bash
head -1 /etc/services
```

```bash
head -1 /etc/services > /tmp/h1
```

```bash
head -1 /etc/services >> /tmp/h1
```

 
<br><br>

> **tail** - output some last lines (default 10) of file STDOUT (default - terminal)

> Օրինակներ
 
```bash
tail /etc/services
```

```bash
tail -1 /etc/services
```

```bash
tail -1 /etc/services > /tmp/s1
```

```bash
tail -1 /etc/services >> /tmp/s1
```

<br><br>

> **grep** - filter lines based on pattern

> Օրինակներ
 
```bash
cat /etc/services | grep http
```

```bash
ls /usr/bin | grep log
```

```bash
ls /usr/bin | grep ^log
```

```bash
ls /usr/bin | grep log$
```



<br><br>

## I/O Redirection

<img src=https://github.com/trainart/introlinuxshell/blob/main/img/io-redir-1.jpg width=50% height=50% >
<br><br>
<img src=https://github.com/trainart/introlinuxshell/blob/main/img/io-redir-2.jpg width=50% height=50% >

> STDOUT - Standard output  		>     >> 

```bash
ls /etc > ~/stdout
```

```bash
ls /etc >> ~/stdout
```

> STDERR - Standard error output		2>   2>>

```bash
ls /e > ~/stdout
``` 

```bash
ls /e > ~/stdout 2> ~/stderr
```

```bash
ls /e > ~/stdout 2> /dev/null
```

<br><br>

## Pipes

Pipeline - Մեկ հրամանի STDOUT-ը ուղարկել այլ հրամանի STDIN-ին

<img src=https://github.com/trainart/introlinuxshell/blob/main/img/pipes-1.jpg width=50% height=50% >

> Օրինակ

```bash
ls /usr/bin | tail -15 | sort -r
```


```bash
ls /usr/bin | tail -15 | sort
```


Նույնը չէ, ինչ հաջորդաբար կատարումը `;`-ով

```bash
ls /usr/bin ; tail -15 ; sort
```

> Հրամանների համակցում

Հրամանները կարելի է համակցել հետևյալ կերպ՝

* **;**	Պարզապես կատարել հրամանները՝ մեկը մյուսի հետևից

* **|**	Փոխանցել առաջին հրամանի ելքի տվյալները (stdout) 
    երկրորդ հրամանի մուտքին (stdin)

* **&&**	Logical AND 
    եթե առաջին հրամանի ելքի կոդը (exit code) 0 է, կատարել երկրորդը

* **||**	Logical OR
    եթե առաջին հրամանի ելքի կոդը (exit code) 0 չէ, կատարել երկրորդը

_( **echo $?**  - ցույց է տալիս վերջին հրամանի ելքի կոդը (exit code) 0=OK)_


> Օրինակներ

```bash
cd /home && pwd
```

```bash
cd /hh && pwd
```
* ՀԱՐՑ՝ ինչպես ազատվել `cd: /hh: No such file or directory` հաղորդագրությունից

```bash
cd /home || echo "Wrong directory"
```
* Փոխեք `/home`-ը `/hh`-ով

```bash
DD=/bin ; [ -d $DD ] ; echo "Exit code is: $?"
```

```bash
DD=/bn ; [ -d $DD ] ; echo "Exit code is: $?"
```

<br><br>

## Text Editors (Խմբագիրներ)

* **nano**		Standard Linux editor - for newcomers - present in most LINUX versions
* **vi /vim**	Standard UNIX editor - for experienced users - present in most UNIX/Linux versions

There are more editors, like **mcedit** or **joe**, which are mostly not installed by default.


### Nano basics

`nano` is an easy to use text editor for UNIX/Linux operating systems. 
It includes all the basic functionality of text editor.
When you run `nano` main commands are displayed at the bottom.

Most commands are prefixed with `^`, which means `Ctrl` key<br> 
*  `^G` means press `Ctrl`+`g`  (NOT `G`)


### Vim/Vi basics

`vim`/`vi` is a very powerful editor UNIX/Linux text editor. 
The reason to know its basics is that it is initially available almost on any UNIX/Linux system.
Even if any other editor will not be present or available to install Vi/Vim will be there to enable you editing text files.
(one way to learn `vi` basics is to type `vimtutor` and follow instructions).

> Vim Modes
* **Command**	- Single keystroke mostly to switch mode ( "**i**" ) or do other actions
* **Insert/Input**	- Main mode to modify text by typing
* **Execute**	- Execute commands within the editor

There is also much rarely used **Visual** mode for highlight or select text for copying, deleting, etc 

<img src=https://github.com/trainart/introlinuxshell/blob/main/img/vim-modes.jpg width=50% height=50% >

> REMEMBER ! 
> If you get confused in which mode you are in <br>
> just **press the `ESC` key a couple of times and start over** with what you were doing.

<br><br>


> Recommended Command:
* **ZZ**    - Save changes in current file if any and quit 

> Other:
 
* **:q**	- Quit when no changes have been made after last save
* **:q!**	- Quit ignoring changes made
* **:wq**	- Save current file and quit
* **:w {file name}** - Save file with specified name

<br><br>


### PRACTICE

Create new file in `vi` editor

* Type `vi testfile1` to open `vi` with new file `testfile1`
* Press the `i` key to switch to **Insert/Input** mode.
* Type something like:

```bash
We are happy to learn
shell programming in Linux
```

* Press the `ESC` key for command mode
* Type `ZZ` to save and quit the file

