# Repro for [#28110](https://github.com/denoland/deno/issues/28110)

This error is only observed on versions of Deno 2.1.5 and onwards.

```bash
# how to encounter error
$ deno check one/mod.ts`
error: Relative import path "@two/mod.ts" not prefixed with / or ./ or ../ and not in import map from "file:///tmp/repro/one/mod.ts"
    at file:///tmp/repro/one/mod.ts:1:23
```

Removing the `importMap` entry from [`./deno.jsonc`](./deno.jsonc) fixes this.
