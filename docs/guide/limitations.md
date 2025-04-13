---
title: ScheduleLua Limitations
description: Current limitations of the ScheduleLua modding API
---

# ScheduleLua Limitations

::: warning Beta Software
ScheduleLua is currently in beta development. Many features are still being implemented and bugs are expected.
:::

## Current Limitations

While ScheduleLua provides a powerful Lua 5.2 scripting environment for Schedule 1, there are several important limitations to be aware of:

### Limited Game Feature Access

- **Partial API Coverage**: Many game systems are not yet accessible through the API
- **In-Development Functions**: Some documented functions may have incomplete implementations
- **Missing Game Systems**: Several core game features don't have corresponding API methods yet

### Known Issues

- **Stability Issues**: Some API functions may crash or behave unexpectedly in certain scenarios
- **Performance Limitations**: Complex scripts may impact game performance, especially when using the `Update()` hook
- **Error Handling**: Error messages may not always clearly indicate the source of problems
- **Hot-Reloading**: Reloading scripts during gameplay may cause unpredictable behavior

### Multiplayer Considerations

::: danger Multiplayer Warning
ScheduleLua does not handle networking or synchronization between game clients. Using ScheduleLua in multiplayer games can cause desyncs, unintended behavior, or crashes.
:::

- **No Network Synchronization**: Changes made by scripts are not synchronized between clients
- **Client-Side Only**: All operations happen locally and are not server-authoritative
- **Potential for Desyncs**: Scripts modifying game state will cause clients to diverge in behavior
- **No Multiplayer Events**: There are no events for networking or player join/leave detection

### Development Roadmap

Many of these limitations are being addressed in ongoing development. Check the [Development Status](/guide/development-status) page for the most up-to-date information on planned features and fixes.

## Best Practices for Working with Limitations

Despite these limitations, you can still create useful scripts by:

- **Testing Thoroughly**: Verify your scripts work as expected in different game scenarios
- **Using Stable APIs**: Focus on using fully implemented features (marked as ✅ in documentation)
- **Error Checking**: Always check return values and implement error handling
- **Performance Optimization**: Minimize work done in frequently called functions like `Update()`
- **Avoiding Multiplayer**: Use scripts in single-player mode only, until multiplayer support is added

## Reporting Issues

If you encounter bugs or unexpected behavior, please report them on the [GitHub issue tracker](https://github.com/ifBars/ScheduleLua/issues) or discuss them in the [Discord community](https://discord.gg/rV2QSAnqhX).

Your feedback is essential for improving ScheduleLua! 