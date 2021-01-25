# React.Component
## Lifecycle Methods
建立 class component 時，lifecycle methods 執行順序，依下列 3 種階段分類

### 新版本

#### Mounting
component 初次渲染時，依序執行
1. [constructor()](/React/TopLevelAPIs/Components/LifecycleMethods/constructor().md)
2. [getDerivedStateFromProps()](/React/TopLevelAPIs/Components/LifecycleMethods/getDerivedStateFromProps().md)
3. [render()](/React/TopLevelAPIs/Components/LifecycleMethods/render().md)
4. [componentDidMount()](/React/TopLevelAPIs/Components/LifecycleMethods/componentDidMount().md)

#### Updating
當 props 或 state 發生改變時，依序執行
1. [getDerivedStateFromProps()](/React/TopLevelAPIs/Components/LifecycleMethods/getDerivedStateFromProps().md)
2. [shouldComponentUpdate()](/React/TopLevelAPIs/Components/LifecycleMethods/shouldComponentUpdate().md)
3. [render()](/React/TopLevelAPIs/Components/LifecycleMethods/render().md)
4. [getSnapshotBeforeUpdate()](/React/TopLevelAPIs/Components/LifecycleMethods/getSnapshotBeforeUpdate().md)
5. [componentDidUpdate()](/React/TopLevelAPIs/Components/LifecycleMethods/componentDidUpdate().md)

#### Unmounting
當 component 將要從 DOM 結構中被移除時，依序執行
1. [componentWillUnmount()](/React/TopLevelAPIs/Components/LifecycleMethods/componentWillUnmount().md)

### diagram
![React Lifecycle Methods diagram](/Images/ReactLifecycleMethodsdiagram.png)

### 其他

#### Error boundaries
在 component 的結構中抓到 JS error 時，讓 component 不至於 crashed，可以正常渲染，因此可以在此做 log、呈現 fallback UI 等且依序執行
1. [getDerivedStateFromError()](/React/TopLevelAPIs/Components/LifecycleMethods/getDerivedStateFromError().md)
2. [componentDidCatch()](/React/TopLevelAPIs/Components/LifecycleMethods/componentDidCatch().md)