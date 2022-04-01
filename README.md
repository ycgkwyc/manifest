# manifest

`chromiumos.xml` 包含了 Google 上游 manifest 中各个项目，并且锁定了 commit id。
其中有若干项目在上游基础上做了修改，已新分支的形式，推到了 openfyde  上。

<!-- markdownlint-disable line-length -->
```xml
<manifest>
  <!-- .... -->
  <extend-project name="chromiumos/overlays/chromiumos-overlay" path="src/third_party/chromiumos-overlay" revision="refs/heads/release-R96-14268.B-fydeos" origRev="refs/heads/release-R96-14268.B" />
  <extend-project name="chromiumos/overlays/portage-stable" path="src/third_party/portage-stable" revision="release-R96-14268.B-fydeos" origRev="refs/heads/release-R96-14268.B" />
  <extend-project name="chromium/tools/depot_tools" path="src/chromium/depot_tools" revision="release-R96-14268.B-fydeos" origRev="09f358bae36c316e3c4c39cd344de964bd0fed7c" />
  <!-- .... -->
</manifest>
```
<!-- markdownlint-enable line-length -->

按照当前的更新模式，在整个 R96 里程碑版本周期内，`chromiumos.xml` 基本不需改动。

`openfyde.xml` 里是 openfyde 添加项目。目前的状态：

* 包含能够编译出 `amd64-openfyde` R96 版本所需的项目

