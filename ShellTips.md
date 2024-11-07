# Shell 命令使用说明

模块使用广播的形式提供Shell接口

```shell
am broadcast -a <行为> <参数> <参数> ...
```

使用Shell接口，需要对Shell命令和安卓部分命令有一定基础，仅供极客使用

## 小窗模式

桌面应用不支持切换小窗

### 切换到普通小窗

切换到普通小窗，支持从全屏、迷你小窗和由普通小窗切换的贴边小窗切换，或者以普通小窗模式打开一个应用

#### 基本命令

```shell
am broadcast -a name.liuyi.mifreeformx.action.SWITCH_TO_FREEFORM
```

#### 参数

- 目标任务id

  ```shell
  --ei task_id xxx
  ```

  xxx为需要控制的任务 id，不设置参数默认优先级为：迷你小窗>贴边小窗>全屏应用。

- 目标应用、目标组件：**使用该参数后，其他参数失效**

  ```shell
  --es component xxx
  ```
  
  xxx 为目标应用、目标组件，如
  
  - 打开微信（com.tencent.mm）
  - 打开微信扫一扫（com.tencent.mm/com.tencent.mm.plugin.scanner.ui.BaseScanUI 或者 com.tencent.mm/.plugin.scanner.ui.BaseScanUI）

### 切换到迷你小窗

切换到迷你小窗，支持从全屏和普通小窗和由迷你小窗切换的贴边的小窗切换

#### 基本命令

```shell
am broadcast -a name.liuyi.mifreeformx.action.SWITCH_TO_MINI_FREEFORM
```

#### 参数

- 目标任务id

  ```shell
  --ei task_id xxx
  ```

  xxx为需要控制的任务 id，不设置参数默认优先级为：普通小窗>贴边小窗>全屏应用。

- 迷你小窗位置

  ```shell
  --ei corner_position xxx
  ```

  xxx为1时是迷你小窗在左上角，2时在右上角，不设置参数默认右上角

### 切换到贴边小窗

切换成贴边小窗，支持从普通小窗、迷你小窗和全屏应用切换

#### 注意

全屏←→贴边小窗：系统并不支持全屏和迷你小窗之间的转换，全屏到贴边小窗需要经过迷你小窗或普通小窗，所以中间可能出现动画鬼畜。

#### 基本命令

```shell
am broadcast -a name.liuyi.mifreeformx.action.SWITCH_TO_PINNED
```

#### 参数

- 目标任务id

  ```shell
  --ei task_id xxx
  ```

  xxx为需要控制的任务 id，不设置参数默认优先级为：普通小窗>迷你小窗>全屏应用。

- 全屏到贴边小窗的过渡模式

  ```shell
  --ei mode xxx
  ```

  xxx为1时，使用普通小窗过渡到贴边小窗，xxx为2时使用迷你小窗，默认使用迷你小窗模式

  使用迷你小窗模式过渡时，还可使用`corner_position`控制迷你小窗的位置

- 过渡延迟：为了减少过渡鬼畜，可以适当加入一点延迟

  ```shell
  --ei delay xxx
  ```

  xxx是过渡的延迟时间，单位**毫秒**，默认为0

### 切换到全屏

切换到全屏，支持从普通小窗、迷你小窗和贴边切换

#### 注意

全屏←→贴边小窗：系统并不支持全屏和迷你小窗之间的转换，贴边小窗到全屏应用需要经过迷你小窗或普通小窗，所以中间可能出现动画鬼畜。

#### 基本命令

```shell
am broadcast -a name.liuyi.mifreeformx.action.SWITCH_TO_FULLSCREEN
```

#### 参数

- 目标任务id

  ```shell
  --ei task_id xxx
  ```

  xxx为需要控制的任务 id，不设置参数默认优先级为：普通小窗>迷你小窗>贴边小窗。

- 过渡模式

  ```shell
  --ei mode xxx
  ```

  xxx为1时，使用普通小窗过渡，xxx为2时使用迷你小窗，默认使用迷你小窗模式

  使用迷你小窗模式过渡时，还可使用`corner_position`控制迷你小窗的位置

- 过渡延迟：为了减少过渡鬼畜，可以适当加入一点延迟

  ```shell
  --ei delay xxx
  ```

  xxx是过渡的延迟时间，单位**毫秒**，默认为0

### 关闭小窗（应用）

将应用放进后台，如果需要关闭应用，请使用`am`或`pm`命令

#### 基本命令

```shell
am broadcast -a name.liuyi.mifreeformx.action.SWITCH_TO_CLOSED
```

#### 参数

- 目标任务id

  ```shell
  --ei task_id xxx
  ```

  xxx为需要控制的任务 id，不设置参数默认优先级为：普通小窗>迷你小窗>贴边小窗>全屏应用。

- 是否在最近任务中移除（仅支持贴边小窗、全屏应用）

  ```shell
  --ei remove_from_recents xxx
  ```

  xxx为1时移除，为0时不移除，默认不移除

