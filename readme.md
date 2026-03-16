# Node.js Proc

Makes it easy to run child processes when the nodejs `node:child_process` module is available.

```ts
import proc from '@grershy/nodejs-proc';
const repoHasChanges = await proc('git status', { cwd: '/path/to/my/repo' }).then(res => {
  return res.output[has]('working tree clean');
});
```

By default `process.env` is passed to `proc`. To control the environment vars, use:
```ts
await proc('my command', { env: { ENV_VAR: 'custom env var' } });
```
