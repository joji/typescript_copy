# ð§anyå

TypeScriptã®anyåã¯ãã©ããªåã§ãä»£å¥ãè¨±ãåã§ããããªããã£ãåã§ãããªãã¸ã§ã¯ãã§ããä½ãä»£å¥ãã¦ãã¨ã©ã¼ã«ãªãã¾ããã

```ts twoslash
let value: any;
value = 1; // OK
value = "string"; // OK
value = { name: "ãªãã¸ã§ã¯ã" }; // OK
```

ã¾ããanyåã®å¤æ°ã«ã¤ãã¦ã¯ãããä»¥ä¸ã³ã³ãã¤ã©ã¼ãåãã§ãã¯ãè¡ãã¾ãããå®è¡ãã¦ã¿ãã¨ã¨ã©ã¼ã«ãªããããªã³ã¼ãã§ããã³ã³ãã¤ã©ã¼ã¯ãã®åé¡ãææãã¾ãããæ¬¡ã®ä¾ã§ã¯ãæ°å¤ãå¤æ°`str`ã«ä»£å¥ãã¦ãã¾ãããããã2è¡ç®ã®`toLowerCase`ã¯æå­ååã®ã¡ã½ããã§æ°å¤åã«ã¯å­å¨ããªãããå®è¡ãã¦ã¿ãã¨ã¨ã©ã¼ã«ãªãã¾ãããã®ãããªåç´ãªçç¾ã¯TypeScriptã³ã³ãã¤ã©ã¼ã§çºè¦ã§ãã¾ãããåæ³¨éã§anyã«ããå¤ã«ã¤ãã¦ã¯ã³ã³ãã¤ã©ã¼ãè­¦åããªããªãã¾ãã

```ts twoslash
const str: any = 123;
str.toLowerCase();
// @error: TypeError: str.toLowerCase is not a function
```

## æé»ã®any

TODO: å¼æ°ã¯åæ³¨éããªãã¨anyã«ãªããã¨ãèª¬æãã

TODO: æé»ã®anyãè¦å¶ãã`noImplicitAny`ãªãã·ã§ã³ãèª¬æãã

[noImplicitAny](../tsconfig/noimplicitany.md)

## anyã¯æªï¼

anyåã¯ã³ã³ãã¤ã©ã¼ã®ãã§ãã¯ãæå¶ãããã¨ãã«ç¨ããç¹å¥ãªåã§ããanyåãæ¿«ç¨ããã¨ãåãã§ãã¯ãå¼±ããªããã°ã®çºè¦ã§ããªããªãæããããã¾ããanyã¯åã®ãã§ãã¯ãæ¾æ£ããåã¨ãè¨ãã¾ãããä¸æ¦ã«æªãã¨ã¯è¨ãåãã¾ãããçç±ãªãanyãä½¿ãã®ã¯åé¡ã§ãããã©ããã¦ãanyãä½¿ããªãã¨ãªããªãå ´é¢ããåå®å¨æ§ãå¦¥åããä¸ã§ãã¾ãã¯åãã³ã¼ããå½¢ã«ãããã¨ãåªåããã¨ãã£ããã¨ããããã¾ããanyãã©ãã¾ã§è¨±å®¹ããããåãã§ãã¯ãã©ãã¾ã§å³æ ¼ã«ãããã¯ããã¼ã ã®çç·´åº¦ããã­ã¸ã§ã¯ãã®æ¹éã«ããã¨ãããå¤§ããã§ãã

## ãããã°ããªãTypeScriptã

TODO: ããã°ããªãTypeScriptã¨ããã¢ãã­ã¼ãããããã¨ãç´¹ä»ããã

## é¢é£æå ±

[ð§unknownå](../statements/unknown.md)

[ð§any vs unknown](../statements/any-vs-unknown.md)
