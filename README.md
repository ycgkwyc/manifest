# manifest

`chromiumos.xml` 包含了 Google 上游 manifest 中各个项目，并且锁定了 commit id。
其中有若干项目在上游基础上做了修改，已新分支的形式，推到了 openfyde gerrit 上。

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
* 项目暂时放在内网 gitlab 上。待稳定后，需要放在 gitee 上，并且 `openfyde.xml`
  文件中的 `remote` 地址和各个项目的 `path` 需要修改为 gitee 上的地址。
* 对项目分支名称的说明
  * `r96-dev` 分支代表已经在原有 `r92` 分支上，为了 R96 版本的编译，做了较多改动
  * `r96` 分支代表在原有 `r92` 分支上直接创建了 `r96` 分支，不需改动；或者该项目
    已经在 R96 版本上稳定。
