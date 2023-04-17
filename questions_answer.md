##### When you login you get “$” prompt, what is the prompt for root?
Answer: # is the default prompt for root. However, this can be changed by editing the `.bashrc` file.
##### Explain the difference between grep and egrep?
`grep` Stands for global regular expression print, uses basic regular expression, so meta-characters such as `| () {} ?` need to be escaped with `\` when using them in a search pattern.
`egrep` Stands for extended global regular expression print, it uses the extended regular expression, so meta-characters don't need to be escaped. The
`grep` command can be extended to work like the `egrep` command by using the `-E` flag. See example below, where the pattern is to search for either apple or banana in the file fruits.
``` console
┌──[14:57:20]─[0]─[root@almanode1:~]
└──| grep 'apple|banana' fruits
┌──[14:57:42]─[0]─[root@almanode1:~]
└──| egrep 'apple|banana' fruits
apple
banana
┌──[14:57:49]─[0]─[root@almanode1:~]
└──| grep -E 'apple|banana' fruits
apple
banana
```
