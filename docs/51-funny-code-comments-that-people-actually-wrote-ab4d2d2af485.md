# 人们实际上写的 51 个有趣的代码注释

> 原文：<https://javascript.plainenglish.io/51-funny-code-comments-that-people-actually-wrote-ab4d2d2af485?source=collection_archive---------13----------------------->

## 读这些评论只是为了好玩

![](img/904d48221cef18364b5a8264279623b8.png)

Photo by [Jimmy Conover](https://unsplash.com/@jimmy_conover?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

代码注释能让你发笑。

当你被一个 bug 卡住，感到沮丧的时候。这些代码注释可以减轻你的情绪。阅读有趣的评论可以帮助你在阅读其他开发者的代码时减轻压力。

很少有人不喜欢写评论。他们试图以一种自文档化的方式编码。但是他们没有意识到，写评论是可以自娱自乐，让别人发笑的。

这里我找到了一些会让你发笑的代码注释。

1.

```
// Sometimes I believe Complier Ignore all my Comments:(
```

2.

```
// When I wrote this, only God and I understood what I was doing
// Now, God only knows
```

3.

```
Exception up = new Exception("Something is really wrong.");
throw up;  //ha ha
```

4.

```
// 
// Dear maintainer:
// 
// Once you are done trying to 'optimize' this routine,
// and have realized what a terrible mistake that was,
// please increment the following counter as a warning
// to the next guy:
// 
// total_hours_wasted_here = 42
//
```

5.

```
// Autogenerated, do not edit. All changes will be undone.
```

6.

```
// I dedicate all this code, all my work, to my wife, Darlene, who 
// will have to support me and our three children and the dog once 
// it gets released into the public.
```

7.

```
// drunk, fix later
```

8.

```
// Magic. Please don't touch.
```

9.

```
#define TRUE FALSE     
//Happy debugging suckers
```

10.

```
// I'm sorry.
```

11.

```
return 1; # returns 1
```

12.

```
/* This is O(scary), but seems quick enough in practice. */
```

13.

```
long john; // silver
```

14.

```
Catch (Exception e) {
 //who cares?
}
```

15.

```
try {

} finally { // should never happen 

}
```

16.

```
const int TEN=10; // As if the value of 10 will fluctuate...
```

17.

```
long long ago; /* in a galaxy far far away */
```

18.

```
// This code sucks, you know it and I know it.  
// Move on and call me an idiot later.
```

19.

```
// If this comment is removed the program will blow up.
```

20.

```
// I am not sure if we need this, but too scared to delete.
```

21.

```
# To understand recursion, see the bottom of this fileThis is written at the end of the file:# To understand recursion, see the top of this file
```

22.

```
// I am not responsible of this code.
// They made me write it, against my will.
```

23.

```
/* Please work */
```

24.

```
/* You are not meant to understand this */
```

25.

```
// I am not sure why this works but it fixes the problem.
```

26.

```
try {

}
catch (SQLException ex) { // Basically, without saying too much, you're screwed. Royally     // and totally.}
catch(Exception ex)
{
    //If you thought you were screwed before, boy have I news for //you!!!
}
```

27.

```
def format_ticket_content(text, recursive = true)
  if text.is_a?(TicketNote)
    note = text
    text = note.content
  else
    note = nil
  end

  ## Safety pig has arrived!
  text = h(text)
  ##                               _
  ##  _._ _..._ .-',     _.._(`))
  ## '-. `     '  /-._.-'    ',/
  ##    )         \            '.
  ##   / _    _    |             \
  ##  |  a    a    /              |
  ##  \   .-.                     ;  
  ##   '-('' ).-'       ,'       ;
  ##      '-;           |      .'
  ##         \           \    /
  ##         | 7  .__  _.-\   \
  ##         | |  |  ``/  /`  /
  ##        /,_|  |   /,_/   /
  ##           /,_/      '`-'
  ##
```

28.

有人在源代码中嵌入了 ASCII 艺术。

```
 ,_-=(!7(7/zs_.             
                                   .='  ' .`/,/!(=)Zm.           
                     .._,,._..  ,-`- `,\ ` -` -`\\7//WW.         
                ,v=~/.-,-\- -!|V-s.)iT-|s|\-.'   `///mK%.        
              v!`i!-.e]-g`bT/i(/[=.Z/m)K(YNYi..   /-]i44M.       
            v`/,`|v]-DvLcfZ/eV/iDLN\D/ZK@%8W[Z..   `/d!Z8m       
           //,c\(2(X/NYNY8]ZZ/bZd\()/\7WY%WKKW)   -'|(][%4\.      
         ,\\i\c(e)WX@WKKZKDKWMZ8(b5/ZK8]Z7%ffVM,   -.Y!bNMi      
         /-iit5N)KWG%%8%%%%W8%ZWM(8YZvD)XN(@.  [   \]!/GXW[      
        / ))G8\NMN%W%%%%%%%%%%8KK@WZKYK*ZG5KMi,-   vi[NZGM[      
       i\!(44Y8K%8%%%**~YZYZ@%%%%%4KWZ/PKN)ZDZ7   c=//WZK%!      
      ,\v\YtMZW8W%%f`,`.t/bNZZK%%W%%ZXb*K(K5DZ   -c\\/KM48       
      -|c5PbM4DDW%f  v./c\[tMY8W%PMW%D@KW)Gbf   -/(=ZZKM8[       
      2(N8YXWK85@K   -'c|K4/KKK%@  V%@@WD8e~  .//ct)8ZK%8`       
      =)b%]Nd)@KM[  !'\cG!iWYK%%|   !M@KZf    -c\))ZDKW%`        
      YYKWZGNM4/Pb  '-VscP4]b@W%     'Mf`   -L\///KM(%W!         
      !KKW4ZK/W7)Z. '/cttbY)DKW%     -`  .',\v)K(5KW%%f          
      'W)KWKZZg)Z2/,!/L(-DYYb54%  ,,`, -\-/v(((KK5WW%f           
       \M4NDDKZZ(e!/\7vNTtZd)8\Mi!\-,-/i-v((tKNGN%W%%            
       'M8M88(Zd))///((|D\tDY\\KK-`/-i(=)KtNNN@W%%%@%[           
        !8%@KW5KKN4///s(\Pd!ROBY8/=2(/4ZdzKD%K%%%M8@%%           
         '%%%W%dGNtPK(c\/2\[Z(ttNYZ2NZW8W8K%%%%YKM%M%%.          
           *%%W%GW5@/%!e]_tZdY()v)ZXMZW%W%%%*5Y]K%ZK%8[          
            '*%%%%8%8WK\)[/ZmZ/Zi]!/M%%%%@f\ \Y/NNMK%%!          
              'VM%%%%W%WN5Z/Gt5/b)((cV@f`  - |cZbMKW%%|          
                 'V*M%%%WZ/ZG\t5((+)L\'-,,/  -)X(NWW%%           
                      `~`MZ/DZGNZG5(((\,    ,t\\Z)KW%@           
                         'M8K%8GN8\5(5///]i!v\K)85W%%f           
                           YWWKKKKWZ8G54X/GGMeK@WM8%@            
                            !M8%8%48WG@KWYbW%WWW%%%@             
                              VM%WKWK%8K%%8WWWW%%%@`             
                                ~*%%%%%%W%%%%%%%@~               
                                   ~*MM%%%%%%@f`                 
                                       '''''
```

29.

```
/*
after hours of consulting the tome of google
i have discovered that by the will of unknown forces
without the below line, IE7 believes that 6px = 12px
*/
font-size: 0px;
```

30.

```
// I can't divide with zero, so I have to divide with something very // similar
result = number / 0.00000000000001;
```

31.

```
// If you're reading this, that means you have been put in charge of // my previous project.
// I am so, so sorry for you. God speed.
```

32.

```
//The following strings are meant to be funny. Do not edit these //strings
//unless you are funny, too.  If you don't know if you're funny, //you're not funny.  If fewer than 2 people unrelated to you have //told you that you're funny, you're not funny.
```

33.

```
//I'm sorry, but our princess is in another castle.
```

34.

```
/* Ah ah ah! You'll never understand why this one works. */
```

35.

```
//this formula is right, work out the math yourself if you don't believe me
```

36.

```
public boolean isDirty() {
    //Why do you always go out and
    return dirty;
}
```

37.

```
public GetRandomNumber()
{
    // Chosen by a fairly rolen dice
    return 10;
}
```

38.

```
//If you even THINK of changing this code, you may have already //gone too far
```

39.

```
//  If you delete the credits, I will fucking kill you.
```

40.

```
// this used to be a comment
```

41.

```
// Since this file is loaded on every page, and since 
  // I want the following function on every page, I'm going to 
  // cheat and include it here even though it has nothing to 
  // do with the other things in this file. 
  // If you don't like it, bite me!
```

42.

```
var arbitraryNumber = 10;
//I don't know why. Just move on.
```

43.

```
// I am not sure if we need this, but too scared to delete.// I have to find a better job// i don’t know why but this seems to work.// Catching exceptions is for communists LOL//Temporary hack for client. Remove on Monday//why am I writing this piece of crap,It can make other’s life //miserable// this is a fucking tragedy…it assumes that the genre filter is //there too, since that’s valid for the only// case this is used in I’m leaving it like this, but it’s shit and //should be fixed. just not now, or probably by me// TODO : Add a commentdouble d; // cupcatch (Exception pokemon) {//gotta catch em all.}entity.setProperty(false); // ALWAYS TRUE
```

44.

```
//Mr. Compiler, please do not read this.
```

45.

```
aComment = 'this is not aComment' # this is aComment
class T(object):
    def f(this):
        this is not aComment
```

46.

```
//If you're reading this, then my program is probably a success
```

47.

```
// Remove this if you wanna be fired
```

48.

```
// This is crap code but it's 3 a.m. and I need to get this working.
```

49.

```
// some sport psychology
if (!focused)
    Focus();
```

50.

```
// This is a walkaround for bug #7812
```

51.

```
// For the sins I am about to commit, may James Gosling forgive me
```

# 参考资料:

1.  源代码中的最佳注释 [StackOverflow](https://stackoverflow.com/questions/184618/what-is-the-best-comment-in-source-code-you-have-ever-encountered)
2.  搞笑代码评论 [Quora](https://www.quora.com/What-are-some-of-the-funniest-comments-in-source-code)

# 想联系作者？

[加入一个人人社区，享受与科技相关的文章。我们讨论最新的技术和独特的见解。](https://codertoentrepreneurs.substack.com/)

*更多内容看* [***说白了就是***](http://plainenglish.io/) ***。*** *报名参加我们的* [***免费每周简讯这里***](http://newsletter.plainenglish.io/) ***。***