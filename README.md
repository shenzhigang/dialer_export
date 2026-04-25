# dialer_export

从当前 AOSP `packages/apps/Dialer` 导出的 Android Studio / Gradle 工程。

特点:

- 主源码已复制到 `app/src/main/aosp`
- AOSP 中的 `.proto` 已预生成到 `app/src/main/generated-proto`
- Dialer 依赖的多份 `AndroidManifest.xml` 已预合并到 `app/src/main/AndroidManifest.xml`
- 少量非 maven 的 AOSP 依赖源码已放到 `app/src/main/compat/java`
- 按 AOSP `aapt2 --auto-add-overlay` 语义预合并了多层资源目录
- 自动生成了 AOSP 多包名资源访问所需的 `R` shim
- 已补齐 `Gradle Wrapper`，可直接使用 `./gradlew`
- 已在当前机器上验证通过 `assembleDebug`

打开方式:

```bash
cd dialer_export
./gradlew assembleDebug
```

如果 Android Studio 未自动识别 SDK，可检查 `local.properties` 中的 `sdk.dir`。

调试包输出:

```text
app/build/outputs/apk/debug/app-debug.apk
```
