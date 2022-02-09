VScode用户设置

1. 打开设置

文件--首选项--设置，打开用户设置。VScode支持选择配置，也支持编辑setting.json文件修改默认配置。个人更倾向于编写json的方式进行配置，下面会附上我个人的配置代码

这里解析几个常用配置项：

（1）editor.fontsize用来设置字体大小，可以设置editor.fontsize : 14;

（2）files.autoSave这个属性是表示文件是否进行自动保存，推荐设置为onFocusChange——文件焦点变化时自动保存。

（3）editor.tabCompletion用来在出现推荐值时，按下Tab键是否自动填入最佳推荐值，推荐设置为on;

（4）editor.codeActionsOnSave中的source.organizeImports属性，这个属性能够在保存时，自动调整 import 语句相关顺序，能够让你的 import 语句按照字母顺序进行排列，推荐设置为true,即"editor.codeActionsOnSave": { "source.organizeImports": true }；

（5）editor.lineNumbers设置代码行号,即editor.lineNumbers ：true；

我的个人配置，供参考：

{
  "files.associations": {
  "*.vue": "vue",
  "*.wpy": "vue",
  "*.wxml": "html",
  "*.wxss": "css"
  },
  "terminal.integrated.shell.windows": "C:\\Windows\\System32\\cmd.exe",
  "git.enableSmartCommit": true,
  "git.autofetch": true,
  "emmet.triggerExpansionOnTab": true,
  "emmet.showAbbreviationSuggestions": true,
  "emmet.showExpandedAbbreviation": "always",
  "emmet.includeLanguages": {
  "vue-html": "html",
  "vue": "html",
  "wpy": "html"
  },
  //主题颜色 
  //"workbench.colorTheme": "Monokai",
  "git.confirmSync": false,
  "explorer.confirmDelete": false,
  "editor.fontSize": 14,
  "window.zoomLevel": 1,
  "editor.wordWrap": "on",
  "editor.detectIndentation": false,
  // 重新设定tabsize
  "editor.tabSize": 2,
  //失去焦点后自动保存
  "files.autoSave": "onFocusChange",
  // #值设置为true时，每次保存的时候自动格式化；
  "editor.formatOnSave": false,
   //每120行就显示一条线
  "editor.rulers": [
  ],
  // 在使用搜索功能时，将这些文件夹/文件排除在外
  "search.exclude": {
      "**/node_modules": true,
      "**/bower_components": true,
      "**/target": true,
      "**/logs": true,
  }, 
  // 这些文件将不会显示在工作空间中
  "files.exclude": {
      "**/.git": true,
      "**/.svn": true,
      "**/.hg": true,
      "**/CVS": true,
      "**/.DS_Store": true,
      "**/*.js": {
          "when": "$(basename).ts" //ts编译后生成的js文件将不会显示在工作空中
      },
      "**/node_modules": true
  }, 
  // #让vue中的js按"prettier"格式进行格式化
  "vetur.format.defaultFormatter.html": "js-beautify-html",
  "vetur.format.defaultFormatter.js": "prettier",
  "vetur.format.defaultFormatterOptions": {
      "js-beautify-html": {
          // #vue组件中html代码格式化样式
          "wrap_attributes": "force-aligned", //也可以设置为“auto”，效果会不一样
          "wrap_line_length": 200,
          "end_with_newline": false,
          "semi": false,
          "singleQuote": true
      },
      "prettier": {
          "semi": false,
          "singleQuote": true
      }
  }
}

最近经常有人微信问我，这个配置代码写在哪里？

新版的vscode设置默认为UI的设置，而非之前的json设置。如果你想复制我上面这段代码进行配置，可以进行下面的修改

文件>首选项>设置 > 搜索workbench.settings.editor，选中json即可改成json设置；

禁用自动更新

文件 > 首选项 > 设置（macOS：代码 > 首选项 > 设置，搜索update mode并将设置更改为none。

开启代码提示设置

第一步：点击左下角点击设置图标，找到并点击“setting”

第二步：到搜索框里搜索“prevent”--->并取消此项的勾选
常用的快捷键

高效的使用vscode,记住一些常用的快捷键是必不可少的，我给大家罗列了一些日常工作过程中用的多的快捷键。

以下以Windows为主，windows的 Ctrl，mac下换成Command就行了

对于 行 的操作：

    重开一行：光标在行尾的话，回车即可；不在行尾，ctrl + enter 向下重开一行；ctrl+shift + enter 则是在上一行重开一行删除一行：光标没有选择内容时，ctrl + x 剪切一行；ctrl +shift + k 直接删除一行移动一行：alt + ↑ 向上移动一行；alt + ↓ 向下移动一行复制一行：shift + alt + ↓ 向下复制一行；shift + alt + ↑ 向上复制一行ctrl + z 回退

对于 词 的操作：

    选中一个词：ctrl + d 

搜索或者替换：

    ctrl + f ：搜索ctrl + alt + f： 替换ctrl + shift + f：在项目内搜索

通过Ctrl + ` 可以打开或关闭终端

Ctrl+P 快速打开最近打开的文件

Ctrl+Shift+N 打开新的编辑器窗口

Ctrl+Shift+W 关闭编辑器

Home 光标跳转到行头

End 光标跳转到行尾

Ctrl + Home 跳转到页头

Ctrl + End 跳转到页尾

Ctrl + Shift + [ 折叠区域代码

Ctrl + Shift + ] 展开区域代码

Ctrl + / 添加关闭行注释

Shift + Alt +A 块区域注释 