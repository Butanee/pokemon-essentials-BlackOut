# Pokémon Essentials

基于 Essentials v21.1。

您可以在此版本库的 fork 上构建您的游戏。这样做可以让你在此版本库有改进时立即更新你的 fangame。

## Usage

1. 复刻此仓库。
2. 获取 Essentials v21.1 的副本（此处无法提供下载链接）。
3. 将复刻的 repo 克隆到 Essentials v21.1 文件夹中，用 repo 中的文件替换现有文件。

在这里，你可以编辑这个项目，把它变成你的 fangame/develop mods。当该版本库更新时，你可以提取更改内容更新你的复刻，并将更新内容导入到你的 fangame/modding 环境中

## Scripts

脚本不再保存在 Scripts.rxdata 文件中。它们已被提取为单独的文件，并放置在 Data/Scripts/ 文件夹（以及其中的子文件夹）中。这样就能更方便地与其他人合作并跟踪更改。

脚本按字母顺序加载到游戏中，从最上面的文件夹（Data/Scripts/）开始，依次深入。也就是说，先加载指定文件夹中的所有脚本，然后依次检查每个子文件夹（同样按字母数字顺序）中需要加载/检查的文件/文件夹。

### Extracting and reintegrating scripts

此 repo 的主文件夹中包含两个脚本文件：

* scripts_extract.rb - 运行该文件可将 Scripts.rxdata 中的所有脚本提取为单独的 .rb 文件（删除任何现有的单独 .rb 文件）。
  * Scripts.rxdata 会被备份到 ScriptsBackup.rxdata，然后会被读取单个 .rb 文件的版本所取代，不会做任何其他操作。
* scripts_combine.rb - 运行此功能可将所有独立的 .rb 文件重新整合回 Scripts.rxdata。
  * 单独的 .rb 文件将保留在原处，但不再执行任何操作。

运行这些脚本需要安装 Ruby。我们的目的是用更友好的方式来替换这些脚本。

## Files not in the repo

* .gitignore 文件列出了该版本中不包含的文件。这些文件是

  * Audio/、Graphics/、Plugins/ 和 Screenshots/ 文件夹及其中的所有文件。
  * Data/ 文件夹中的所有文件，但以下文件除外：
    * Data/Scripts/ 文件夹及其中的所有内容。
    * Scripts.rxdata（只加载单个脚本文件的特殊版本）。
    * messages_core.dat 文件夹，其中包含常用信息，对翻译项目非常有用。
  * 主项目文件夹中的一些文件（两个 Game.xxx 文件、RGSS dll 文件和 errorlog.txt）。
  * 临时文件。
