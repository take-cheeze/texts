* [bash reference](http://www.gnu.org/software/bash/manual/bashref.html)
* [syslog setting in OS X](http://www.madbavoo.com/syslog/)
* [deleting specific line with sed](http://stackoverflow.com/questions/5410757/sed-delete-a-line-containing-a-specific-string)
* [removing BOM](http://stackoverflow.com/questions/1068650/using-awk-to-remove-the-byte-order-mark)
  * sed way: sed -i '1 s/^\xef\xbb\xbf//' *.txt
* [how to implement watch command with shell script](http://blog.majide.com/2006/01/how-to-use-linux-watch-command/)
  * use sleep

## basename
* [example](http://stackoverflow.com/questions/125281/how-do-i-remove-the-file-suffix-and-path-portion-from-a-path-string-in-bash)
```
 basename /tmp/local.hhh .hhh # -> local

```

* [extension, filename, basename with bash](http://d.hatena.ne.jp/te2u/20090327/p1)
  * ${var##*/} : basename
  * ${var%.*} : filename
  * [how to use # in bash](http://sonic64.com/2006-02-27.html)

## Comment
* use "#" on beginning of line for single line comment
* Multi line comment
* [example](http://www.cyberciti.biz/faq/bash-comment-out-multiple-line-code/)
```
 <<COMMENT1
   a
   b
   c
 COMMENT1

```

* Also can be used to embed other script
  * [How to embed python script](http://stackoverflow.com/questions/2189098/embedding-short-python-scripts-inside-a-bash-script)

## If
* [tutorial](http://shellscript.sunone.me/if_and_test.html)
* Don't forget the whitespace between expression and semicolon.
* [Or, And](http://d.hatena.ne.jp/yohei-a/20090622/1245638171)
  * use "-a" or "-o" option in test

<code> 
 if exp ; then
   # do something
 else exp2 ; then
   # do something
 elif
   # do something
 fi

```

{| border="1" class="article-table" style="width: 500px;"
! scope="col"| Expression
! scope="col"| result
|-
| [ -d $dir ] || true if the $dir exists and is directory
|-
| [ -f $file ] || true if the $file exists. false if $file directory
|}