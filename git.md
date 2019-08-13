<!DOCTYPE html>
<!-- saved from url=(0025)https://www.mdeditor.com/ -->
<html lang="zh" style=""><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Markdown在线编辑器 - MdEditor</title>
    <meta name="keywords" content="markdown在线编辑器,online markdown editor,markdown编辑器,在线编辑markdown,mdeditor">
    <meta name="description" content="mdeditor是一个在线编辑markdown的工具">
    <link rel="stylesheet" href="./git.md_files/style.css">
    <link rel="stylesheet" href="./git.md_files/editormd.min.css">
    <link rel="shortcut icon" href="https://www.mdeditor.com/images/logos/favicon.ico" type="image/x-icon">
    <script src="./git.md_files/osd.js.下载"></script><script src="./git.md_files/show_ads_impl.js.下载" id="google_shimpl"></script><script src="./git.md_files/hm.js.下载"></script><script>
        var _hmt = _hmt || [];
        (function() {
            var hm = document.createElement("script");
            hm.src = "https://hm.baidu.com/hm.js?076c2cebde2229783d44f7f8cd54d2a4";
            var s = document.getElementsByTagName("script")[0];
            s.parentNode.insertBefore(hm, s);
        })();
    </script>
<link rel="preload" href="./git.md_files/integrator.js.下载" as="script"><script type="text/javascript" src="./git.md_files/integrator.js.下载"></script><link rel="preload" href="./git.md_files/show_ads_impl.js.下载" as="script"><link type="text/css" rel="stylesheet" href="./git.md_files/codemirror.min.css"><link type="text/css" rel="stylesheet" href="./git.md_files/dialog.css"><link type="text/css" rel="stylesheet" href="./git.md_files/matchesonscrollbar.css"><link type="text/css" rel="stylesheet" href="./git.md_files/foldgutter.css"><script id="-lib-codemirror-codemirror-min" type="text/javascript" src="./git.md_files/codemirror.min.js.下载"></script><script id="-lib-codemirror-modes-min" type="text/javascript" src="./git.md_files/modes.min.js.下载"></script><script id="-lib-codemirror-addons-min" type="text/javascript" src="./git.md_files/addons.min.js.下载"></script><link type="text/css" rel="stylesheet" href="./git.md_files/eclipse.css"><script id="-lib-marked-min" type="text/javascript" src="./git.md_files/marked.min.js.下载"></script><script id="-lib-prettify-min" type="text/javascript" src="./git.md_files/prettify.min.js.下载"></script><script id="-lib-raphael-min" type="text/javascript" src="./git.md_files/raphael.min.js.下载"></script><script id="-lib-underscore-min" type="text/javascript" src="./git.md_files/underscore.min.js.下载"></script><script id="-lib-flowchart-min" type="text/javascript" src="./git.md_files/flowchart.min.js.下载"></script><script id="-lib-jquery-flowchart-min" type="text/javascript" src="./git.md_files/jquery.flowchart.min.js.下载"></script><script id="-lib-sequence-diagram-min" type="text/javascript" src="./git.md_files/sequence-diagram.min.js.下载"></script><link type="text/css" rel="stylesheet" href="./git.md_files/katex.min.css"><script id="-cdnjs-cloudflare-com-ajax-libs-KaTeX-0-3-0-katex-min" type="text/javascript" src="./git.md_files/katex.min.js.下载"></script><style id="tsbrowser_video_independent_player_style" type="text/css">
      [tsbrowser_force_max_size] {
        width: 100% !important;
        height: 100% !important;
        left: 0px !important;
        top: 0px !important;
        margin: 0px !important;
        padding: 0px !important;
      }
      [tsbrowser_force_fixed] {
        position: fixed !important;
        z-index: 9999 !important;
        background: black !important;
      }
      [tsbrowser_force_hidden] {
        opacity: 0 !important;
        z-index: 0 !important;
      }
      [tsbrowser_hide_scrollbar] {
        overflow: hidden !important;
      }</style><script id="-lib-plugins-image-dialog-image-dialog" type="text/javascript" src="./git.md_files/image-dialog.js.下载"></script></head>
<body style="">
<div id="layout">
    <div id="test-editormd" style="width: 1366px; height: 583px;" class="editormd editormd-vertical editormd-theme-eclipse editormd-fullscreen"><textarea class="editormd-markdown-textarea" placeholder="Enjoy Markdown! coding now..." name="test-editormd-markdown-doc" style="display: none;"># git 手册


创建版本库

	mkdir //文件夹名称
	git init  //生成.git
	git add 文件名
	git commit -m "注释"


版本回退

	git log
	git log --pretty=oneline 
	git reset --hard HEAS^   //回到上一个版本
	git reset --hard 1094a   //1094a是ID号
	git reflog   //记录的每条命令
	git status  //查看状态

管理修改

	//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git commit
	git diff HEAD -- readme.txt   //第二次修改不会被提交
	//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git add -&gt; git commit
	git diff HEAD -- readme.txt  //第二次修改被提交了
撤销修改

	git checkout -- readme.txt //意思就是，把readme.txt文件在工作区的修改全部撤销
	//一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
	//一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
	//总之，就是让这个文件回到最近一次git commit或git add时的状态。
	注意：git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令

删除文件

	git rm test.txt   //删除文件
	git commit -m ''  //提交一下
	git checkout -- test.txt  //误删的可以恢复最新版本

分支管理
创建分支

	git checkout -b dev   //创建dev分支并且切换到dev
	//下两句同git checkout -b dev
	git branch dev
	git checkout dev
	//
	git branch    //查看所有分支
	git merge dev  //合并dev分区到master上
	git merge --no-ff -m "merge with no-ff" dev //合并分支表示禁用Fast forward
	//合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。
	git branch -d dev //删除dev分支
	git checkout master //完成工作后切换到master
	//几步
	查看分支：git branch
	创建分支：git branch &lt;name&gt;
	切换分支：git checkout &lt;name&gt;
	创建+切换分支：git checkout -b &lt;name&gt;
	合并某分支到当前分支：git merge &lt;name&gt;
	删除分支：git branch -d &lt;name&gt;

冲突

	git status    //查看冲突文件
	git log --graph --pretty=oneline --abbrev-commit
bug分支

	git stash  //可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作
	确定要在哪个分支上修复bug，假定需要在master分支上修复，就从master创建临时分支

	git stash list  //查看储藏现场
	//恢复现场
	//一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；
	//另一种方式是用git stash pop，恢复的同时把stash内容也删了
	git stash apply stash@{0}  //恢复指定的stash

Feature分支

	//销毁没有（不能）合并的分支
	git branch -d feature-vulcan  //销毁分支的时候提示没有提交不能销毁
	git branch -D feature-vulcan  // -D 强制删除

分支管理策略

	git remote -v //显示更详细的远程库信息
	//显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址

	推送分支
	//就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上
	git push origin master
	git push origin dev
	//master分支是主分支，因此要时刻与远程同步；
	//dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
	//bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
	//feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

	抓取分支
	git clone git@github.com:michaelliao/learngit.git
	git checkout -b dev origin/dev    //创建远程origin的dev分支到本地
	//另一个人对同样的文件作了修改
	git push origin dev //推送失败
	git pull  //也失败了,原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接
	git branch --set-upstream-to=origin/dev dev
	//再pull,git pull成功，但是合并有冲突，需要手动解决,解决后，提交，再push

多人协作的工作模式通常

	//首先，可以试图用git push origin &lt;branch-name&gt;推送自己的修改；
	//如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
	//如果合并有冲突，则解决冲突，并在本地提交；
	//没有冲突或者解决掉冲突后，再用git push origin &lt;branch-name&gt;推送就能成功！

rebase

	 git rebase //rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。
 忽略特殊文件
 
	 .gitignore文件  //把要忽略的文件名填进去，Git就会自动忽略这些文件
	 git add -f App.class //强制添加
	 git check-ignore -v App.class  //Git会告诉我们，.gitignore的第几行规则忽略了该文件

配置别名

	 git config --global alias.st status  //status变成st
	 git config --global alias.unstage 'reset HEAD'  //reset HEAD'变成unstage




</textarea><div class="CodeMirror cm-s-eclipse CodeMirror-wrap" style="font-size: 13px; width: 684px; margin-top: 133px; height: 451px;"><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 180px; left: 242.953px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" style="position: absolute; padding: 0px; width: 1000px; height: 1em; outline: none;" tabindex="0"></textarea></div><div class="CodeMirror-vscrollbar" cm-not-content="true" style="bottom: 0px; display: block;"><div style="min-width: 1px; height: 3113px;"></div></div><div class="CodeMirror-hscrollbar" cm-not-content="true"><div style="height: 100%; min-height: 1px; width: 0px;"></div></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 49px; margin-bottom: -7px; border-right-width: 23px; min-height: 3110px; padding-right: 7px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines"><div style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre>x</pre><div class="CodeMirror-linenumber CodeMirror-gutter-elt"><div>1</div></div><div class="CodeMirror-linenumber CodeMirror-gutter-elt"><div>141</div></div></div><div class="CodeMirror-measure"><pre><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">//没有冲突或者解决掉冲突后，再用git push origin &lt;branch-name&gt;推送就能成功！</span></span></pre></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-cursors" style=""><div class="CodeMirror-cursor" style="left: 193.953px; top: 176px; height: 22px;">&nbsp;</div></div><div class="CodeMirror-code" style=""><div class="" style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">1</div><div class="CodeMirror-gutter-elt" style="left: 39px; width: 9px;"><div class="CodeMirror-foldgutter-open CodeMirror-guttermarker-subtle"></div></div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-header cm-header-1"># git 手册</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">2</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div class="" style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">3</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">4</div></div><pre class=""><span style="padding-right: 0.1px;">创建版本库</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">5</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">6</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">mkdir //文件夹名称</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">7</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git init  //生成.git</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">8</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git add 文件名</span></span></pre></div><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">9</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git commit -m "注释"</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">10</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">11</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">12</div></div><pre class=""><span style="padding-right: 0.1px;">版本回退</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">13</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">14</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git log</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">15</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git log --pretty=oneline</span><span class="cm-comment cm-cm-overlay cm-trailingspace"> </span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">16</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git reset --hard HEAS^ &nbsp; //回到上一个版本</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">17</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git reset --hard 1094a &nbsp; //1094a是ID号</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">18</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git reflog &nbsp; //记录的每条命令</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">19</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git status  //查看状态</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">20</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">21</div></div><pre class=""><span style="padding-right: 0.1px;">管理修改</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">22</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">23</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git commit</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">24</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git diff HEAD -- readme.txt &nbsp; //第二次修改不会被提交</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">25</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git add -&gt; git commit</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">26</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git diff HEAD -- readme.txt  //第二次修改被提交了</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">27</div></div><pre class=""><span style="padding-right: 0.1px;">撤销修改</span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">28</div></div><pre class=""><span style="padding-right: 0.1px;"><span cm-text="">​</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">29</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">git checkout -- readme.txt //意思就是，把readme.txt文件在工作区的修改全部撤销</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">30</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">//一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；</span></span></pre></div><div style="position: relative;"><div class="CodeMirror-gutter-wrapper" style="left: -49px; width: 49px;"><div class="CodeMirror-linenumber CodeMirror-gutter-elt" style="left: 0px; width: 21px;">31</div></div><pre class=""><span style="padding-right: 0.1px;"><span class="cm-tab" role="presentation" cm-text="	">    </span><span class="cm-comment">//一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。</span></span></pre></div></div></div></div></div></div><div style="position: absolute; height: 23px; width: 1px; top: 3110px;"></div><div class="CodeMirror-gutters" style="height: 3133px;"><div class="CodeMirror-gutter CodeMirror-linenumbers" style="width: 29px;"></div><div class="CodeMirror-gutter CodeMirror-foldgutter"></div></div></div></div><a href="javascript:;" class="fa fa-close editormd-preview-close-btn"></a>
<textarea class="editormd-html-textarea" name="test-editormd-html-code">&lt;h1 id="h1-git-"&gt;&lt;a name="git 手册" class="reference-link"&gt;&lt;/a&gt;&lt;span class="header-link octicon octicon-link"&gt;&lt;/span&gt;git 手册&lt;/h1&gt;&lt;p&gt;创建版本库&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;mkdir //文件夹名称
git init  //生成.git
git add 文件名
git commit -m "注释"
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;版本回退&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git log
git log --pretty=oneline 
git reset --hard HEAS^   //回到上一个版本
git reset --hard 1094a   //1094a是ID号
git reflog   //记录的每条命令
git status  //查看状态
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;管理修改&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;//第一次修改 -&amp;gt; git add -&amp;gt; 第二次修改 -&amp;gt; git commit
git diff HEAD -- readme.txt   //第二次修改不会被提交
//第一次修改 -&amp;gt; git add -&amp;gt; 第二次修改 -&amp;gt; git add -&amp;gt; git commit
git diff HEAD -- readme.txt  //第二次修改被提交了
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;撤销修改&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git checkout -- readme.txt //意思就是，把readme.txt文件在工作区的修改全部撤销
//一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
//一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
//总之，就是让这个文件回到最近一次git commit或git add时的状态。
注意：git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;删除文件&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git rm test.txt   //删除文件
git commit -m ''  //提交一下
git checkout -- test.txt  //误删的可以恢复最新版本
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;分支管理&lt;br&gt;创建分支
&lt;pre&gt;&lt;code&gt;git checkout -b dev   //创建dev分支并且切换到dev
//下两句同git checkout -b dev
git branch dev
git checkout dev
//
git branch    //查看所有分支
git merge dev  //合并dev分区到master上
git merge --no-ff -m "merge with no-ff" dev //合并分支表示禁用Fast forward
//合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。
git branch -d dev //删除dev分支
git checkout master //完成工作后切换到master
//几步
查看分支：git branch
创建分支：git branch &amp;lt;name&amp;gt;
切换分支：git checkout &amp;lt;name&amp;gt;
创建+切换分支：git checkout -b &amp;lt;name&amp;gt;
合并某分支到当前分支：git merge &amp;lt;name&amp;gt;
删除分支：git branch -d &amp;lt;name&amp;gt;
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;冲突&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git status    //查看冲突文件
git log --graph --pretty=oneline --abbrev-commit
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;bug分支&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git stash  //可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作
确定要在哪个分支上修复bug，假定需要在master分支上修复，就从master创建临时分支

git stash list  //查看储藏现场
//恢复现场
//一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；
//另一种方式是用git stash pop，恢复的同时把stash内容也删了
git stash apply stash@{0}  //恢复指定的stash
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;Feature分支&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;//销毁没有（不能）合并的分支
git branch -d feature-vulcan  //销毁分支的时候提示没有提交不能销毁
git branch -D feature-vulcan  // -D 强制删除
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;分支管理策略&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;git remote -v //显示更详细的远程库信息
//显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址

推送分支
//就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上
git push origin master
git push origin dev
//master分支是主分支，因此要时刻与远程同步；
//dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
//bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
//feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

抓取分支
git clone git@github.com:michaelliao/learngit.git
git checkout -b dev origin/dev    //创建远程origin的dev分支到本地
//另一个人对同样的文件作了修改
git push origin dev //推送失败
git pull  //也失败了,原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接
git branch --set-upstream-to=origin/dev dev
//再pull,git pull成功，但是合并有冲突，需要手动解决,解决后，提交，再push
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;多人协作的工作模式通常&lt;/p&gt;
&lt;pre&gt;&lt;code&gt;//首先，可以试图用git push origin &amp;lt;branch-name&amp;gt;推送自己的修改；
//如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
//如果合并有冲突，则解决冲突，并在本地提交；
//没有冲突或者解决掉冲突后，再用git push origin &amp;lt;branch-name&amp;gt;推送就能成功！
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;rebase&lt;/p&gt;
&lt;pre&gt;&lt;code&gt; git rebase //rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt; 忽略特殊文件&lt;/p&gt;
&lt;pre&gt;&lt;code&gt; .gitignore文件  //把要忽略的文件名填进去，Git就会自动忽略这些文件
 git add -f App.class //强制添加
 git check-ignore -v App.class  //Git会告诉我们，.gitignore的第几行规则忽略了该文件
&lt;/code&gt;&lt;/pre&gt;&lt;p&gt;配置别名&lt;/p&gt;
&lt;pre&gt;&lt;code&gt; git config --global alias.st status  //status变成st
 git config --global alias.unstage 'reset HEAD'  //reset HEAD'变成unstage
&lt;/code&gt;&lt;/pre&gt;</textarea>
<div class="editormd-preview editormd-preview-theme-eclipse" style="display: block; width: 683px; top: 133px; height: 451px;"><div class="markdown-body editormd-preview-container" previewcontainer="true" style="padding: 20px;"><h1 id="h1-git-"><a name="git 手册" class="reference-link"></a><span class="header-link octicon octicon-link"></span>git 手册</h1><p>创建版本库</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">mkdir </span><span class="com">//文件夹名称</span></code></li><li class="L1"><code><span class="pln">git init  </span><span class="com">//生成.git</span></code></li><li class="L2"><code><span class="pln">git add </span><span class="pun">文件名</span></code></li><li class="L3"><code><span class="pln">git commit </span><span class="pun">-</span><span class="pln">m </span><span class="str">"注释"</span></code></li></ol></pre><p>版本回退</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git log</span></code></li><li class="L1"><code><span class="pln">git log </span><span class="pun">--</span><span class="pln">pretty</span><span class="pun">=</span><span class="pln">oneline </span></code></li><li class="L2"><code><span class="pln">git reset </span><span class="pun">--</span><span class="pln">hard HEAS</span><span class="pun">^</span><span class="pln">   </span><span class="com">//回到上一个版本</span></code></li><li class="L3"><code><span class="pln">git reset </span><span class="pun">--</span><span class="pln">hard </span><span class="lit">1094a</span><span class="pln">   </span><span class="com">//1094a是ID号</span></code></li><li class="L4"><code><span class="pln">git reflog   </span><span class="com">//记录的每条命令</span></code></li><li class="L5"><code><span class="pln">git status  </span><span class="com">//查看状态</span></code></li></ol></pre><p>管理修改</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="com">//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git commit</span></code></li><li class="L1"><code><span class="pln">git diff HEAD </span><span class="pun">--</span><span class="pln"> readme</span><span class="pun">.</span><span class="pln">txt   </span><span class="com">//第二次修改不会被提交</span></code></li><li class="L2"><code><span class="com">//第一次修改 -&gt; git add -&gt; 第二次修改 -&gt; git add -&gt; git commit</span></code></li><li class="L3"><code><span class="pln">git diff HEAD </span><span class="pun">--</span><span class="pln"> readme</span><span class="pun">.</span><span class="pln">txt  </span><span class="com">//第二次修改被提交了</span></code></li></ol></pre><p>撤销修改</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git checkout </span><span class="pun">--</span><span class="pln"> readme</span><span class="pun">.</span><span class="pln">txt </span><span class="com">//意思就是，把readme.txt文件在工作区的修改全部撤销</span></code></li><li class="L1"><code><span class="com">//一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；</span></code></li><li class="L2"><code><span class="com">//一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。</span></code></li><li class="L3"><code><span class="com">//总之，就是让这个文件回到最近一次git commit或git add时的状态。</span></code></li><li class="L4"><code><span class="pun">注意：</span><span class="pln">git checkout </span><span class="pun">--</span><span class="pln"> file</span><span class="pun">命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令</span></code></li></ol></pre><p>删除文件</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git rm test</span><span class="pun">.</span><span class="pln">txt   </span><span class="com">//删除文件</span></code></li><li class="L1"><code><span class="pln">git commit </span><span class="pun">-</span><span class="pln">m </span><span class="str">''</span><span class="pln">  </span><span class="com">//提交一下</span></code></li><li class="L2"><code><span class="pln">git checkout </span><span class="pun">--</span><span class="pln"> test</span><span class="pun">.</span><span class="pln">txt  </span><span class="com">//误删的可以恢复最新版本</span></code></li></ol></pre><p>分支管理<br>创建分支
</p><pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git checkout </span><span class="pun">-</span><span class="pln">b dev   </span><span class="com">//创建dev分支并且切换到dev</span></code></li><li class="L1"><code><span class="com">//下两句同git checkout -b dev</span></code></li><li class="L2"><code><span class="pln">git branch dev</span></code></li><li class="L3"><code><span class="pln">git checkout dev</span></code></li><li class="L4"><code><span class="com">//</span></code></li><li class="L5"><code><span class="pln">git branch    </span><span class="com">//查看所有分支</span></code></li><li class="L6"><code><span class="pln">git merge dev  </span><span class="com">//合并dev分区到master上</span></code></li><li class="L7"><code><span class="pln">git merge </span><span class="pun">--</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">ff </span><span class="pun">-</span><span class="pln">m </span><span class="str">"merge with no-ff"</span><span class="pln"> dev </span><span class="com">//合并分支表示禁用Fast forward</span></code></li><li class="L8"><code><span class="com">//合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。</span></code></li><li class="L9"><code><span class="pln">git branch </span><span class="pun">-</span><span class="pln">d dev </span><span class="com">//删除dev分支</span></code></li><li class="L0"><code><span class="pln">git checkout master </span><span class="com">//完成工作后切换到master</span></code></li><li class="L1"><code><span class="com">//几步</span></code></li><li class="L2"><code><span class="pun">查看分支：</span><span class="pln">git branch</span></code></li><li class="L3"><code><span class="pun">创建分支：</span><span class="pln">git branch </span><span class="str">&lt;name&gt;</span></code></li><li class="L4"><code><span class="pun">切换分支：</span><span class="pln">git checkout </span><span class="str">&lt;name&gt;</span></code></li><li class="L5"><code><span class="pun">创建+切换分支：</span><span class="pln">git checkout </span><span class="pun">-</span><span class="pln">b </span><span class="str">&lt;name&gt;</span></code></li><li class="L6"><code><span class="pun">合并某分支到当前分支：</span><span class="pln">git merge </span><span class="str">&lt;name&gt;</span></code></li><li class="L7"><code><span class="pun">删除分支：</span><span class="pln">git branch </span><span class="pun">-</span><span class="pln">d </span><span class="str">&lt;name&gt;</span></code></li></ol></pre><p>冲突</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git status    </span><span class="com">//查看冲突文件</span></code></li><li class="L1"><code><span class="pln">git log </span><span class="pun">--</span><span class="pln">graph </span><span class="pun">--</span><span class="pln">pretty</span><span class="pun">=</span><span class="pln">oneline </span><span class="pun">--</span><span class="pln">abbrev</span><span class="pun">-</span><span class="pln">commit</span></code></li></ol></pre><p>bug分支</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git stash  </span><span class="com">//可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作</span></code></li><li class="L1"><code><span class="pun">确定要在哪个分支上修复</span><span class="pln">bug</span><span class="pun">，假定需要在</span><span class="pln">master</span><span class="pun">分支上修复，就从</span><span class="pln">master</span><span class="pun">创建临时分支</span></code></li><li class="L2"><code></code></li><li class="L3"><code><span class="pln">git stash list  </span><span class="com">//查看储藏现场</span></code></li><li class="L4"><code><span class="com">//恢复现场</span></code></li><li class="L5"><code><span class="com">//一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；</span></code></li><li class="L6"><code><span class="com">//另一种方式是用git stash pop，恢复的同时把stash内容也删了</span></code></li><li class="L7"><code><span class="pln">git stash apply stash@</span><span class="pun">{</span><span class="lit">0</span><span class="pun">}</span><span class="pln">  </span><span class="com">//恢复指定的stash</span></code></li></ol></pre><p>Feature分支</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="com">//销毁没有（不能）合并的分支</span></code></li><li class="L1"><code><span class="pln">git branch </span><span class="pun">-</span><span class="pln">d feature</span><span class="pun">-</span><span class="pln">vulcan  </span><span class="com">//销毁分支的时候提示没有提交不能销毁</span></code></li><li class="L2"><code><span class="pln">git branch </span><span class="pun">-</span><span class="pln">D feature</span><span class="pun">-</span><span class="pln">vulcan  </span><span class="com">// -D 强制删除</span></code></li></ol></pre><p>分支管理策略</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln">git remote </span><span class="pun">-</span><span class="pln">v </span><span class="com">//显示更详细的远程库信息</span></code></li><li class="L1"><code><span class="com">//显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址</span></code></li><li class="L2"><code></code></li><li class="L3"><code><span class="pun">推送分支</span></code></li><li class="L4"><code><span class="com">//就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上</span></code></li><li class="L5"><code><span class="pln">git push origin master</span></code></li><li class="L6"><code><span class="pln">git push origin dev</span></code></li><li class="L7"><code><span class="com">//master分支是主分支，因此要时刻与远程同步；</span></code></li><li class="L8"><code><span class="com">//dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；</span></code></li><li class="L9"><code><span class="com">//bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；</span></code></li><li class="L0"><code><span class="com">//feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。</span></code></li><li class="L1"><code></code></li><li class="L2"><code><span class="pun">抓取分支</span></code></li><li class="L3"><code><span class="pln">git clone git@github</span><span class="pun">.</span><span class="pln">com</span><span class="pun">:</span><span class="pln">michaelliao</span><span class="pun">/</span><span class="pln">learngit</span><span class="pun">.</span><span class="pln">git</span></code></li><li class="L4"><code><span class="pln">git checkout </span><span class="pun">-</span><span class="pln">b dev origin</span><span class="pun">/</span><span class="pln">dev    </span><span class="com">//创建远程origin的dev分支到本地</span></code></li><li class="L5"><code><span class="com">//另一个人对同样的文件作了修改</span></code></li><li class="L6"><code><span class="pln">git push origin dev </span><span class="com">//推送失败</span></code></li><li class="L7"><code><span class="pln">git pull  </span><span class="com">//也失败了,原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接</span></code></li><li class="L8"><code><span class="pln">git branch </span><span class="pun">--</span><span class="kwd">set</span><span class="pun">-</span><span class="pln">upstream</span><span class="pun">-</span><span class="pln">to</span><span class="pun">=</span><span class="pln">origin</span><span class="pun">/</span><span class="pln">dev dev</span></code></li><li class="L9"><code><span class="com">//再pull,git pull成功，但是合并有冲突，需要手动解决,解决后，提交，再push</span></code></li></ol></pre><p>多人协作的工作模式通常</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="com">//首先，可以试图用git push origin &lt;branch-name&gt;推送自己的修改；</span></code></li><li class="L1"><code><span class="com">//如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；</span></code></li><li class="L2"><code><span class="com">//如果合并有冲突，则解决冲突，并在本地提交；</span></code></li><li class="L3"><code><span class="com">//没有冲突或者解决掉冲突后，再用git push origin &lt;branch-name&gt;推送就能成功！</span></code></li></ol></pre><p>rebase</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln"> git rebase </span><span class="com">//rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。</span></code></li></ol></pre><p> 忽略特殊文件</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln"> </span><span class="pun">.</span><span class="pln">gitignore</span><span class="pun">文件</span><span class="pln">  </span><span class="com">//把要忽略的文件名填进去，Git就会自动忽略这些文件</span></code></li><li class="L1"><code><span class="pln"> git add </span><span class="pun">-</span><span class="pln">f </span><span class="typ">App</span><span class="pun">.</span><span class="kwd">class</span><span class="pln"> </span><span class="com">//强制添加</span></code></li><li class="L2"><code><span class="pln"> git check</span><span class="pun">-</span><span class="pln">ignore </span><span class="pun">-</span><span class="pln">v </span><span class="typ">App</span><span class="pun">.</span><span class="kwd">class</span><span class="pln">  </span><span class="com">//Git会告诉我们，.gitignore的第几行规则忽略了该文件</span></code></li></ol></pre><p>配置别名</p>
<pre class="prettyprint linenums prettyprinted" style=""><ol class="linenums"><li class="L0"><code><span class="pln"> git config </span><span class="pun">--</span><span class="kwd">global</span><span class="pln"> </span><span class="kwd">alias</span><span class="pun">.</span><span class="pln">st status  </span><span class="com">//status变成st</span></code></li><li class="L1"><code><span class="pln"> git config </span><span class="pun">--</span><span class="kwd">global</span><span class="pln"> </span><span class="kwd">alias</span><span class="pun">.</span><span class="pln">unstage </span><span class="str">'reset HEAD'</span><span class="pln">  </span><span class="com">//reset HEAD'变成unstage</span></code></li></ol></pre></div></div>
<div class="editormd-container-mask" style="display: none;"></div>
<div class="editormd-mask" style="background-color: rgb(255, 255, 255); opacity: 0.1; z-index: 99998; display: none;"></div><div class="editormd-toolbar" style="display: block;"><div class="editormd-toolbar-container"><ul class="editormd-menu"><li><a href="javascript:;" title="撤销（Ctrl+Z）" unselectable="on"><i class="fa fa-undo" name="undo" unselectable="on"></i></a></li><li><a href="javascript:;" title="重做（Ctrl+Y）" unselectable="on"><i class="fa fa-repeat" name="redo" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="粗体" unselectable="on"><i class="fa fa-bold" name="bold" unselectable="on"></i></a></li><li><a href="javascript:;" title="删除线" unselectable="on"><i class="fa fa-strikethrough" name="del" unselectable="on"></i></a></li><li><a href="javascript:;" title="斜体" unselectable="on"><i class="fa fa-italic" name="italic" unselectable="on"></i></a></li><li><a href="javascript:;" title="引用" unselectable="on"><i class="fa fa-quote-left" name="quote" unselectable="on"></i></a></li><li><a href="javascript:;" title="将每个单词首字母转成大写" unselectable="on"><i class="fa" name="ucwords" style="font-size:20px;margin-top: -3px;">Aa</i></a></li><li><a href="javascript:;" title="将所选转换成大写" unselectable="on"><i class="fa fa-font" name="uppercase" unselectable="on"></i></a></li><li><a href="javascript:;" title="将所选转换成小写" unselectable="on"><i class="fa" name="lowercase" style="font-size:24px;margin-top: -10px;">a</i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="标题1" unselectable="on"><i class="fa editormd-bold" name="h1" unselectable="on">H1</i></a></li><li><a href="javascript:;" title="标题2" unselectable="on"><i class="fa editormd-bold" name="h2" unselectable="on">H2</i></a></li><li><a href="javascript:;" title="标题3" unselectable="on"><i class="fa editormd-bold" name="h3" unselectable="on">H3</i></a></li><li><a href="javascript:;" title="标题4" unselectable="on"><i class="fa editormd-bold" name="h4" unselectable="on">H4</i></a></li><li><a href="javascript:;" title="标题5" unselectable="on"><i class="fa editormd-bold" name="h5" unselectable="on">H5</i></a></li><li><a href="javascript:;" title="标题6" unselectable="on"><i class="fa editormd-bold" name="h6" unselectable="on">H6</i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="无序列表" unselectable="on"><i class="fa fa-list-ul" name="list-ul" unselectable="on"></i></a></li><li><a href="javascript:;" title="有序列表" unselectable="on"><i class="fa fa-list-ol" name="list-ol" unselectable="on"></i></a></li><li><a href="javascript:;" title="横线" unselectable="on"><i class="fa fa-minus" name="hr" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="链接" unselectable="on"><i class="fa fa-link" name="link" unselectable="on"></i></a></li><li><a href="javascript:;" title="引用链接" unselectable="on"><i class="fa fa-anchor" name="reference-link" unselectable="on"></i></a></li><li><a href="javascript:;" title="添加图片" unselectable="on"><i class="fa fa-picture-o" name="image" unselectable="on"></i></a></li><li><a href="javascript:;" title="行内代码" unselectable="on"><i class="fa fa-code" name="code" unselectable="on"></i></a></li><li><a href="javascript:;" title="预格式文本 / 代码块（缩进风格）" unselectable="on"><i class="fa fa-file-code-o" name="preformatted-text" unselectable="on"></i></a></li><li><a href="javascript:;" title="代码块（多语言风格）" unselectable="on"><i class="fa fa-file-code-o" name="code-block" unselectable="on"></i></a></li><li><a href="javascript:;" title="添加表格" unselectable="on"><i class="fa fa-table" name="table" unselectable="on"></i></a></li><li><a href="javascript:;" title="日期时间" unselectable="on"><i class="fa fa-clock-o" name="datetime" unselectable="on"></i></a></li><li><a href="javascript:;" title="Emoji表情" unselectable="on"><i class="fa fa-smile-o" name="emoji" unselectable="on"></i></a></li><li><a href="javascript:;" title="HTML实体字符" unselectable="on"><i class="fa fa-copyright" name="html-entities" unselectable="on"></i></a></li><li><a href="javascript:;" title="插入分页符" unselectable="on"><i class="fa fa-newspaper-o" name="pagebreak" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="跳转到行" unselectable="on"><i class="fa fa-terminal" name="goto-line" unselectable="on"></i></a></li><li><a href="javascript:;" title="关闭实时预览" unselectable="on"><i class="fa fa-eye-slash" name="watch" unselectable="on"></i></a></li><li><a href="javascript:;" title="全窗口预览HTML（按 Shift + ESC还原）" unselectable="on"><i class="fa fa-desktop" name="preview" unselectable="on"></i></a></li><li><a href="javascript:;" title="清空" unselectable="on"><i class="fa fa-eraser" name="clear" unselectable="on"></i></a></li><li><a href="javascript:;" title="搜索" unselectable="on"><i class="fa fa-search" name="search" unselectable="on"></i></a></li><li class="divider" unselectable="on">|</li><li><a href="javascript:;" title="使用帮助" unselectable="on"><i class="fa fa-question-circle" name="help" unselectable="on"></i></a></li><li><a href="javascript:;" title="关于Editor.md" unselectable="on"><i class="fa fa-info-circle" name="info" unselectable="on"></i></a></li><li><a href="javascript:;" title="" unselectable="on"><i class="fa fa-download" name="download" unselectable="on"></i></a></li></ul></div><div><script async="" src="./git.md_files/adsbygoogle.js.下载"></script><!--mdeditor首页横幅--><ins class="adsbygoogle" style="display:inline-block;width:970px;height:90px" data-ad-client="ca-pub-5770542122007372" data-ad-slot="1145369323" data-adsbygoogle-status="done"><ins id="aswift_0_expand" style="display:inline-table;border:none;height:90px;margin:0;padding:0;position:relative;visibility:visible;width:970px;background-color:transparent;"><ins id="aswift_0_anchor" style="display:block;border:none;height:90px;margin:0;padding:0;position:relative;visibility:visible;width:970px;background-color:transparent;"><iframe width="970" height="90" frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" allowfullscreen="true" onload="var i=this.id,s=window.google_iframe_oncopy,H=s&amp;&amp;s.handlers,h=H&amp;&amp;H[i],w=this.contentWindow,d;try{d=w.document}catch(e){}if(h&amp;&amp;d&amp;&amp;(!d.body||!d.body.firstChild)){if(h.call){setTimeout(h,0)}else if(h.match){try{h=s.upd(h,i)}catch(e){}w.location.replace(h)}}" id="aswift_0" name="aswift_0" style="left:0;position:absolute;top:0;border:0px;width:970px;height:90px;" src="./git.md_files/saved_resource.html"></iframe></ins></ins></ins><script>(adsbygoogle=window.adsbygoogle||[]).push({});</script></div></div><div class="editormd-dialog editormd-image-dialog" id="editormd-image-dialog-1565669358752" style="display: none; z-index: 99999; width: 380px; height: 254px; top: 164.5px; left: 493px;"><div class="editormd-dialog-header" style="cursor: move;"><strong class="editormd-dialog-title">添加图片</strong></div><a href="javascript:;" class="fa fa-close editormd-dialog-close"></a><div class="editormd-dialog-container"><div class="editormd-form"><br><label>图片描述</label><input type="text" value="" data-alt=""><br><label>图片链接</label><input type="text" value="http://" data-link=""><br></div><div class="editormd-dialog-footer"><button class="editormd-btn editormd-enter-btn">确定</button><button class="editormd-btn editormd-cancel-btn">取消</button></div></div><div class="editormd-dialog-mask editormd-dialog-mask-bg"></div><div class="editormd-dialog-mask editormd-dialog-mask-con"></div></div></div>
</div>
<script src="./git.md_files/jquery.min.js.下载"></script>
<script src="./git.md_files/editormd.js.下载"></script>
<script src="./git.md_files/light.js.下载"></script>

<ins class="adsbygoogle adsbygoogle-noablate" data-adsbygoogle-status="done" style="display: none !important;"><ins id="aswift_1_expand" style="display:inline-table;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;"><ins id="aswift_1_anchor" style="display:block;border:none;height:0px;margin:0;padding:0;position:relative;visibility:visible;width:0px;background-color:transparent;"><iframe frameborder="0" marginwidth="0" marginheight="0" vspace="0" hspace="0" allowtransparency="true" scrolling="no" allowfullscreen="true" onload="var i=this.id,s=window.google_iframe_oncopy,H=s&amp;&amp;s.handlers,h=H&amp;&amp;H[i],w=this.contentWindow,d;try{d=w.document}catch(e){}if(h&amp;&amp;d&amp;&amp;(!d.body||!d.body.firstChild)){if(h.call){setTimeout(h,0)}else if(h.match){try{h=s.upd(h,i)}catch(e){}w.location.replace(h)}}" id="aswift_1" name="aswift_1" style="left:0;position:absolute;top:0;border:0px;width:0px;height:0px;" src="./git.md_files/saved_resource(1).html"></iframe></ins></ins></ins><iframe id="google_osd_static_frame_9506467080648" name="google_osd_static_frame" style="display: none; width: 0px; height: 0px;" src="./git.md_files/saved_resource(2).html"></iframe><i title="Raphaël Colour Picker" style="display: none; color: white;"></i></body><iframe id="google_esf" name="google_esf" src="./git.md_files/zrt_lookup.html" data-ad-client="ca-pub-5770542122007372" style="display: none;"></iframe></html>