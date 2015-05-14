#git初体验
<blockquote>
    <p>
        <span style="font-size: 18px;">Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.</span>
    </p>
</blockquote>
<p>
    <span style="font-size: 18px;">这是在Google找到的git的介绍，就是说呀,git是一个免费、开源的分布式版本控制系统，可以高效地处理或大或小的项目。</span></span></span></span>
</p>
<p>
    <span style="font-size: 18px;">这也是它与传统版本控制系统的最大区别，从而解决了原来的很多问题。简单的说吧，就是你只要是参与在这个项目里面，就算服务器崩溃了，也总能找到最全的那个版本，再不会像以前一样丢失了。这就是它强大的地方。当然，还有很多新功能，如果A和B先后想要将文件push到服务器上，在Apush之后，B只需要将最新的版本pull下，再push上去就可以了，不会出现被锁住的问题等等。</span>
</p>
<p>
    <span style="font-size: 18px;">以上是我对git的一种理解吧，虽然是第二次接触git，却发现，先前那次只能算是了解，就连最基本的概念都不清楚，只是很机械地敲着git add之类的命令。</span>
</p>
<p>
    <span style="font-size: 18px;">请允许我先附上一张单词表，这是我在学习www.try.github.io 时所遇到的盲词，也为了日后，可以快速地了解和掌握。</span>
</p>
<p>
    <span style="line-height: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; font-size: 12px; background-color: rgb(246, 246, 246);"></span>
</p>
<table style="height: 87px;">
    <tbody>
        <tr>
            <td style="-ms-word-break: break-all;">
                <span style="line-height: 22.5px; font-size: 18px;">repository &nbsp;n.知识库</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 18px;">remote &nbsp; adj. &nbsp;远程</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 18px;">&nbsp; feature &nbsp; n. 特点 &nbsp;v.放映</span>
            </td>
        </tr>
        <tr>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 18px;">origin &nbsp; n.来源</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 18px;">staged &nbsp; adj. 上演</span>
            </td>
            <td style="-ms-word-break: break-all;"></td>
        </tr>
    </tbody>
</table>
<h3>
    一、git的配置
</h3>
<p>
    <span style="font-size: 18px;">1.git下载安装之后，进行全局变量的配置，告诉git你的名字和邮箱，这样它就<span style="font-size: 16px;">能知道自己的主人是谁了。</span></span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git config --global user.name&quot;name&quot;
git config --global user.email email@email.com</pre>
<p>
    <span style="font-size: 18px;"></span>
</p>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">2.设置git默认的编辑器，我用的是Atom。</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --global core.editor atom</pre>
<p>
    <span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span><br/>
</p>
<p>
    <span style="font-size: 18px;">3.查看基本信息是否配置成功，可以这样</span><br/>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --list</pre>
<p>
    <br/><span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span>
</p>
<p>
    <span style="font-size: 18px;">4.太多了？只想看用户名。可以！</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config username</pre>
<p>
    <span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span><br/>
</p>
<p>
    <span style="font-size: 18px;">做完了基本操作，我们就要用git进行对文件的一系列操作。</span>
</p>
<h3>
    <span style="font-size: 24px;">二、git和github的基本操作</span>
</h3>
<p>
    <span style="font-size: 18px;">首先，你需要创建一个新的空的github 知识库，用来存放你将要上传到服务器上的文件。</span>
</p>
<p>
    <span style="font-size: 18px;">这时候，不要急于把文件放到临时区或者服务器上，要先初始化。</span>
</p>
<p>
    <span style="font-size: 18px;">(注意了，初始化的时候要关注你的当前工作在哪。git的初始化不要在home下。一旦建立在home下，以后的add,commit会把home下的其它目录追踪上去)</span>
</p>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">1.git</span><span style="font-size: 18px;">初始化，生成一个.git的目录，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git init</pre>
<p>
    <br/><span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span>
</p>
<p>
    <span style="font-size: 18px;">2.将文件添加到临时区，追加跟踪</span><br/>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git add &lt;filename&gt;</pre>
<p>
    <br/>
</p>
<p>
    <span style="font-size: 18px;">3.在使用过程中，注意时刻查看当前状态</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git status</pre>
<p>
    <span style="font-size: 18px;">（有三种状态:untracked,staged,commited）</span>
</p>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">4.提交关于修改的说明，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git commit -m&quot;修改说明&quot;</pre>
<p>
    <span style="font-size: 18px;">注意这个说明是要有意义的，这能更方便你快速找到这次的commit,-m就是message的意思。</span><br/><span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span>
</p>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">5.把本地仓库和远程仓库链接起来，</span><br/>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git remote add origin https://</pre>
<p>
    <span style="font-size: 18px;">(如果配置了SSH密钥，地址就应该用SSH的地址，否则密钥无效)</span>
</p>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">6.将文件push到github上 ，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;">git push -u origin master</pre>
<p>
    <span style="font-size: 18px;">(-u是提示git记住参数，master是当地的主要分支)</span>
</p>
<p>
    <span style="font-size: 18px;">最后，输入你的用户名和密码就可以啦。</span>
</p>
<p>
    <span style="font-size: 18px;">什么，每次输入太麻烦？</span>
</p>
<p>
    <span style="font-size: 18px;">那我们就来说说SSH的配置吧。</span>
</p>
<h3>
    <span style="font-size: 24px;">三、SSH Key的配置</span>
</h3>
<p>
    <span style="font-size: 18px;">1.查一下电脑上的SSH目录</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> ls -al的~/ .ssh</pre>
<p>
    <span style="font-size: 18px;"><br/></span>
</p>
<p>
    <span style="font-size: 18px;">2.生成新的SSH密钥，</span><br/>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> ssh-keygen -t rsa -C &quot;email@email.com&quot;</pre>
<p>
    <span style="font-size: 18px;">(这里的email一定是你github的邮箱）</span>
</p>
<p>
    <br/>
</p>
<p>
    <span style="font-size: 18px;">3.配置ssh-agent，先要启用SSH代理，然后把SSH key 添加到 ssh-agent，</span><span style="font-size: 18px;"><br/></span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> eval &quot;$(ssh-agent -s)&quot;
 ssh-add ~/.ssh/id_rsa</pre>
<p>
    <br/><span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span>
</p>
<p>
    <span style="font-size: 18px;">4.添加SSH Key到账户</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> sudo apt-get install xclip
 xclip -sel clip &lt; ~/.ssh/id_rsa.pub</pre>
<p>
    <span style="font-size: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; line-height: 18px; background-color: rgb(246, 246, 246);"></span><br/>
</p>
<p>
    <span style="font-size: 18px;">打开github的settings设置，在SSH keys里添加 &nbsp;Add SSH key，这时候你会发现SSH Key在你的剪贴板里，把它放到Key里面就可以了。</span>
</p>
<p>
    <span style="font-size: 18px;">SSH Key不仅可以方便你不用重复输入，更能安全地管理你的文件。</span>
</p>
<hr/>
<p>
    <span style="font-size: 18px;">以上仅是我这两天接触的到git的皮毛，却也是受益良多。<span style="font-size: 18px; line-height: 22.5px;">写下这篇“初体验”，不仅是为了巩固这几天学到的内容，也希望在将来，忘了某个命令的我，可以多个解决问题的出口。</span></span>
</p>
<p>
    <br/>
</p>
