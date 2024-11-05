# Mob Psycho:
## Question:
So question reads: <br>
Can you handle APKs? Download the android apk [here](https://artifacts.picoctf.net/c_titan/141/mobpsycho.apk). <br>

--

## Solution:
I download the file, it's an apk, I try to run it on my android device, doesn't work.<br>
I try to unxip it, as the hint says, can't do it on windows atleast, the tags call it online shell solvable, I look for an online apk extractor<br>
[found one](http://www.javadecompilers.com/apk).<br>
I send the file through and get the files extracted. The files are too many to manually sort through of course.<br>
I open it in the termninal, and try searching for files with "picoCTF" in them using: ``grep -r "picoCTF" /home/variable/Downloads/mobpsycho.apk_Decompiler.com``<br>
Doesn't work, so it's hidden, I try to look for any human readable strings, to no avail. SO i finally seardh for ``.txt`` files on a random hunch<br>
```find /home/variable/Downloads/mobpsycho.apk_Decompiler.com -type f -name "*.txt"```<br>
hit<br>
I then open it to see....... numbers.<br>
```
7069636f4354467b6178386d433052553676655f4e5838356c346178386d436c5f62313132616535377d
```
Of course. Then I go to cyberchef and convert from hex, and voila ``picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_b112ae57}``.
Which is accepted as the flag.
