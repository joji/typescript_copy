# ð§strictFunctionTypes

ãªãªã¼ã¹ããããã¼ã¸ã§ã³: 2.6

ãªãã¸ã§ã¯ãæåã§ã¯ãã¹ã¼ãã¼ã¯ã©ã¹ã«å¯¾ããµãã¯ã©ã¹ã®ã¤ã³ã¹ã¿ã³ã¹ãä»£å¥ãããã¨ã¯ã§ãã¾ãããã®éã¯ä¸è¬çã§ã¯ããã¾ããã
ãã¨ãã°JavaScriptã® `Error` ã¯ã©ã¹ãæ¡å¼µãã¹ã¿ãã¯ãã¬ã¼ã¹ãåºåã§ããããã«ãªã£ã `RuntimeError` ã¨ããã¯ã©ã¹ãç¨æãã¾ããããã§ã¯ã¹ã¿ãã¯ãã¬ã¼ã¹ã®å®è£ã¯éè¦ã§ã¯ãªãã®ã§ `stacktrace()` ã¨ããã¡ã½ãããå ãã£ãã¨ã ãè§£éãã¦ãã ããã

```typescript
class RuntimeError extends Error {
  public stacktrace(): string {
    return "...";
  }
}
```

`RuntimeError` ã¯ã©ã¹ã®ã¹ã¿ãã¯ãã¬ã¼ã¹ãåºåããé¢æ° `dumpRuntimeError()` ãå®ç¾©ãã¾ããå½ç¶ãªãã `RuntimeError` ã®ã¤ã³ã¹ã¿ã³ã¹ã¯ä»£å¥ã§ãã¾ããã¹ã¼ãã¼ã¯ã©ã¹ã® `Error` ãä»£å¥ãããã¨ã¯ã§ãã¾ããã

```typescript
function dumpRuntimeError(err: RuntimeError): void {
  console.log(err.stacktrace());
}

dumpRuntimeError(new RuntimeError("runtime error"));
dumpRuntimeError(new Error("error"));
```

```text
error TS2345: Argument of type 'Error' is not assignable to parameter of type 'RuntimeError'.
  Property 'stacktrace' is missing in type 'Error' but required in type 'RuntimeError'.

errorDump(new Error('error'));
          ~~~~~~~~~~~~~~~~~~
```

ããããªãã `dumpRuntimeError` åã®é¨ååã§ãã `dumpError` ã¨ããåãå®ç¾©ããã¨ããã¨ãæ¬¡ã®ä»£å¥ãæãç«ã¡ã¾ãã

```typescript
type dumpError = (err: Error) => void;
const dumpError: dumpError = dumpRuntimeError;
```

ãã®é¢æ° `dumpError()` ã« `Error` åã®ã¤ã³ã¹ã¿ã³ã¹ãä»£å¥ããã¨ `Error` åã«ã¯ `stacktrace()` ã¨ããã¡ã½ããããªãããå®è¡æã¨ã©ã¼ã«ãªãã¾ãã

ãã®ãªãã·ã§ã³ãæå¹ã«ãããã¨ã§é¢æ°ã®å¼æ°ã®æ¹ã¯å³å¯ã«è©ä¾¡ãããããã«ãªãã¾ãããã®ã¯ã©ã¹ã¾ãã¯ãµãã¯ã©ã¹ä»¥å¤ãä»£å¥ãããã¨ã¯ã§ããªããªãã¾ãã

```text
error TS2322: Type '(err: RuntimeError) => void' is not assignable to type 'dumpError'.
  Types of parameters 'err' and 'err' are incompatible.
    Property 'stacktrace' is missing in type 'Error' but required in type 'RuntimeError'.

const dumpError: dumpError = dumpRuntimeError;
      ~~~~~~~~~
```

TODO: æ¬¡ã«ã¤ãã¦æ¸ã

- ã¡ã½ããæ§æ(method syntax)ã«ã¯å¹ããªã
- é¢æ°æ§æ(function syntax)ã«ã ãå¹ã
- TSã®å¼æ°ã¯åãbivariantä»æ§
- strictFunctionTypesã¯ãããcontravariantã«ãã
- ã¡ã½ããã¾ã§ããã¨äºææ§çã«åé¡ããã
- ãªã®ã§ã¡ã½ããã¯é¤å¤ãbivariantã®ã¾ã¾
