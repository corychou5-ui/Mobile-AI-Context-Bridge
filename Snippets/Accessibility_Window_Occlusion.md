# Handling Window Occlusion in Accessibility Service

### Problem Description
When an overlay window covers a significant portion of the screen, Android's `AccessibilityManagerService` may exclude the underlying Activity from the window list, leading to incomplete UI metadata extraction.

### Key Insights
- **Root Cause:** System resource optimization and privacy protection for obscured windows.
- **Academic Term:** Window Visibility Contention / UI Hierarchy Occlusion.

### Solutions
1. **Window Size Optimization:** Reduce overlay dimensions below the system's "full-screen" threshold.
2. **Window List Iteration:** Use `getWindows()` instead of `rootInActiveWindow` to manually identify background layers.
3. **Flag Manipulation:** Toggle `FLAG_NOT_TOUCHABLE` to pass events through.

### Keywords
- `AccessibilityNodeInfo`
- `Window-switching logic`
- `Multi-window state representation`