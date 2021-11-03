# 引擎

类型：`EngineInterface`

## 属性

### `options`

选项

类型：`EngineOptions`

### `readonly`

是否只读

类型：`boolean`

### `change`

编辑时状态

类型：`ChangeInterface`

### `typing`

按键处理

类型：`TypingInterface`

### `ot`

协同编辑相关

类型：`OTInterface`

### `history`

历史记录

类型：`HistoryInterface`

### `request`

网络请求

类型：`RequestInterface`

## 方法

### `focus`

聚焦到编辑器

```ts
/**
 * 聚焦到编辑器
 * @param start 是否聚焦的开始位置，默认为 true，false 为聚焦到结束位置
 */
focus(start?: boolean): void;
```

### `isFocus`

当前光标是否已聚焦到编辑器

```ts
/**
 * 当前光标是否已聚焦到编辑器
 */
isFocus(): boolean;
```

### `isEmpty`

当前编辑器是否为空值

```ts
/**
 * 当前编辑器是否为空值
 */
isEmpty(): boolean;
```

### `getValue`

获取编辑器值

```ts
/**
 * 获取编辑器值
 * @param ignoreCursor 是否包含光标位置信息
 */
getValue(ignoreCursor?: boolean): string;
```

### `getValueAsync`

异步获取编辑器值，将等候插件处理完成后再获取值

```ts
/**
 * 异步获取编辑器值，将等候插件处理完成后再获取值
 * 比如插件上传等待中，将等待上传完成后再获取值
 * @param ignoreCursor 是否包含光标位置信息
 */
getValueAsync(ignoreCursor?: boolean): Promise<string>;
```

### `getHtml`

获取编辑器的 html

```ts
/**
 * 获取编辑器的html
 */
getHtml(): string;
```

### `getJsonValue`

获取 JSON 格式的值

```ts
/**
 * 获取JSON格式的值
 */
getJsonValue(): string | undefined | (string | {})[];
```

### `setValue`

设置编辑器值

```ts
/**
 * 设置编辑器值
 * @param value 值
 * @param options 异步渲染卡片回调
 */
setValue(value: string, callback?: (count: number) => void): EngineInterface;
```

### `setHtml`

设置 html 作为编辑器值

```ts
/**
* 设置html，会格式化为合法的编辑器值
* @param html html
* @param options 异步渲染卡片回调
*/
setHtml(html: string, callback?: (count: number) => void): EngineInterface
```

### `setJsonValue`

设置 json 格式值，主要用于与协同服务端的值同步

```ts
/**
 * 设置json格式值，主要用于协同
 * @param value 值
 */
setJsonValue(value: Array<any>): EngineInterface;
```

### `setScrollNode`

设置编辑器滚动条节点

```ts
setScrollNode(node?: HTMLElement)
```

### `destroy`

销毁编辑器

```ts
destroy():void
```