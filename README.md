# airt

> Fast start typescript node.js project

Use cluster auto fork code at file save;

## Install

```sh
yarn add airt typescript tslib -D
```

add package.json

```json
{
  "scripts": {
    "dev": "airt src -w",
    "build": "airt src"
  }
}
```

## Use

Run Dev Server:

```sh
yarn dev
```

Build release

```sh
yarn build
```

## static dir

airt copy `static/` to `dir`;

## Set out dir and static dir

```sh
out=build static=public yarn dev
```

## keepDependencies

airt 默认会排除依赖的编译, 若有确定需要编译的依赖对象, 如 link 的本地资源，请配置 package.keepDependencies 属性，如

package.json:

```json
{
  "keepDependencies": {
    "clino": 1,
    "clino-client": 1
  }
}
```

此时 airt 会编译 clino 库到 dist 中

## copyFiles

airt 默认会拷贝以下文件到 dist 中

```
.env
package-lock.json
pnpm-lock.yaml
yarn.lock
```

若需要增加其他文件，可以配置 package.json 的 copyFiles 属性：

package.json:

```json
{
  "copyFiles": [".env.local", ".env.test"]
}
```
