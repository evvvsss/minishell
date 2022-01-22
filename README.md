# minishell
 The objective of this project is for you to create a simple shell. Your little bash or zsh. You will learn a lot about processes and file descriptors.
# export
Подумайте над следующим примером:

$ a=linuxcareer.com  
$ echo $a  
linuxcareer.com  
$ bash  
$ echo $a  

$  
Строка 1: создается новая переменная с именем "a", содержащая строку "linuxcareer.com".  
Строка 2: мы используем команду echo, чтобы вывести содержимое переменной "a".  
Строка 3: мы создаем дочерний экземпляр оболочки bash.  
Строка 4: переменная "a" теперь не определена.  

Из приведенного выше примера можно видеть, что любой дочерний процесс, ответвляющийся от родительского процесса, по умолчанию не наследует переменные родителя. Для этого и нужна команда export. Что произойдет, если мы используем команду export в вышеприведенном примере?

$ a=linuxcareer.com  
$ echo $a  
linuxcareer.com  
$ export a  
$ bash  
$ echo $a  
linuxcareer.com  
$  
Теперь в строке 3 мы использовали команду export, чтобы экспортировать переменную "a" в созданный новый дочерний процесс. В результате переменная "a" все еще содержит строку "linuxcareer.com", даже после создания нового экземпляра оболочки bash. Здесь важно отметить, что для успешного экспорта "a" необходимо, чтобы процесс, в который экспортируется переменная, ответвлялся от того родительского процесса, из которого экспортируется эта переменная. Связь между дочерним и родительским процессами описана ниже.
 # unset
 Сбрасывает значение переменной  
 
# Разница между одинарными ' и двойными " кавычками
Single quotes won't interpolate anything, but double quotes will. For example: variables, backticks, certain \ escapes, etc.

Example:  

$ echo "$(echo "upg")"  
upg  
$ echo '$(echo "upg")'  
$(echo "upg")  
