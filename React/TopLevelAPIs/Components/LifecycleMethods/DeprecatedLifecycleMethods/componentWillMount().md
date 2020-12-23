# componentWillMount()
1. 往後版本會被移除，若需使用，前方需要加上 **UNSAFE_**，即 UNSAFE_componentWillMount()
2. 在 constructor() 後執行，因此在此執行 setState() 不會 2 次執行 render()
3. 避免在此做 [side-effect](/其他筆記/side-effect.md)
4. SSR 時，只有此 lifecycle method 被執行