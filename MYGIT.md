#git初体验
<blockquote>
    <p>
        <span style="font-size: 16px;">Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.</span>
    </p>
</blockquote>
<p>
    <span style="font-size: 16px;">这是在Google找到的git的介绍，恩，太抽象了我看不懂。</span>
</p>
<p>
    <span style="font-size: 16px;">git作为一个高效的版本控制系统，与传统版本控制系统的最大区别就在于它是分布式的，而且是开源的，这就解决了原来的很多问题。简单的说吧，就是你只要是参与在这个项目里面，就算服务器奔溃了，也总能找到最全的那个版本，再不会像以前一样丢失了。这就是它强大的地方。当然，还有很多新功能，如果A和B先后想要将文件push到服务器上，在Apush之后，B只需要将最新的版本pull下，再push上去就可以了，不会出现被锁住的问题等等。</span>
</p>
<p>
    <span style="font-size: 16px;">以上是我对git的一种理解吧，虽然是第二次接触git，却发现，先前那次只能算是了解，就连最基本的概念都不清楚，只是很机械地敲着git add之类的命令。</span>
</p>
<p>
    <span style="font-size: 16px;">请允许我附上一张单词表，这是我在学习www.try.github.io 时所遇到的盲词，也为了日后回过头来，可以快速地了解和掌握。</span>
</p>
<p>
    <span style="line-height: 18px; font-family: Consolas, 微软雅黑, monospace, Verdana, sans-serif, 宋体; font-size: 12px; background-color: rgb(246, 246, 246);"></span>
</p>
<table style="height: 87px;">
    <tbody>
        <tr class="firstRow">
            <td style="-ms-word-break: break-all;">
                <span style="line-height: 22.5px; font-size: 16px;">repository &nbsp;n.知识库</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 16px;">remote &nbsp; adj. &nbsp;远程</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 16px;">&nbsp; feature &nbsp; n. 特点 &nbsp;v.放映</span>
            </td>
        </tr>
        <tr>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 16px;">origin &nbsp; n.来源</span>
            </td>
            <td style="-ms-word-break: break-all;">
                <span style="font-size: 16px;">staged &nbsp; adj. 上演</span>
            </td>
            <td style="-ms-word-break: break-all;"></td>
        </tr>
    </tbody>
</table>
<p>
    <span style="font-size: 16px;">将git下载安装之后，先要对它进行一个简单的配置，告诉git你的名字和邮箱，这样它就能知道自己的主人是谁了。</span><br/>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --global user.name&quot;wengjiaojiao&quot;</pre>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --global user.email&quot;wengjiaojiao@outlook.com&quot;</pre>
<p>
    <span style="font-size: 16px;">（global代表全局变量，还有一个locate）</span>
</p>
<p>
    <span style="font-size: 16px;">由于会用到文本编辑器，所以在这里还要设置一下git默认的编辑器，我用的是Atom。</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --global core.editor atom</pre>
<p>
    <span style="font-size: 16px;">基本信息就这样配置完成了，如果你想看是否配置成功，可以这样</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config --list</pre>
<p>
    <span style="font-size: 16px;">太多了？我只想看我的用户名。可以！</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git config username</pre>
<p>
    <span style="font-size: 16px;">做完了基本操作，我们就要用git进行对文件的一系列操作。</span>
</p>
<p>
    <span style="font-size: 16px;">首先，你需要创建一个新的空的github 知识库，用来存放你将要上传到服务器上的文件。</span>
</p>
<p>
    <span style="font-size: 16px;">之后，在本地创建一个文件，我创建了一个标题为my-blog的README.md，&nbsp;</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> echo &quot;#my-blog&quot; &gt;&gt; README.md</pre>
<p>
    <span style="font-size: 16px;">这时候，不要急于把文件放到临时区或者服务器上，要先初始化。</span>
</p>
<p>
    <span style="font-size: 16px;">(注意了，初始化的时候要关注你的当前工作在哪。git的初始化不要在home下。一旦建立在home下，以后的add,commit会把home下的其它目录追踪上去)</span>
</p>
<p>
    <span style="font-size: 16px;">所以我先创建了一个子目录Jgit，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> mkdir Jgit</pre>
<p>
    <span style="font-size: 16px;">然后进行初始化，会生成一个.git的目录，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git init</pre>
<p>
    <span style="font-size: 16px;">接下来，需要将文件添加到临时区，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git add README.md</pre>
<p>
    <span style="font-size: 16px;">注意，要时刻查看你的状态</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git status</pre>
<p>
    <span style="font-size: 16px;">（有三种状态:untracked,staged,commited）</span>
</p>
<p>
    <span style="font-size: 16px;">提交关于你修改的说明，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git commit -m&quot;first commit&quot;</pre>
<p>
    <span style="font-size: 16px;">注意这个说明是要有意义的，这能更方便你快速找到这次的commit,-m就是message的意思。</span>
</p>
<p>
    <span style="font-size: 16px;">然后，你需要把本地仓库和远程仓库链接起来，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git remote add origin https://github.com/wengjiaojiao/my-blog</pre>
<p>
    <span style="font-size: 16px;">(如果你在以后配置了SSH密钥，这里的地址就应该用SSH的地址，否则密钥无效)</span>
</p>
<p>
    <span style="font-size: 16px;">之后，告诉git把准备好的commit push到哪里 ，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> git push -u origin master</pre>
<p>
    <span style="font-size: 16px;">(-u是提示git记住参数，master是当地的主要分支)</span>
</p>
<p>
    <span style="font-size: 16px;">最后，输入你的用户名和密码就可以啦。</span>
</p>
<p>
    <span style="font-size: 16px;">什么，每次输入太麻烦？</span>
</p>
<p>
    <span style="font-size: 16px;">那我们就来说说SSH的配置吧。</span>
</p>
<p>
    <span style="font-size: 16px;">首先，让我们检查一下电脑上是否已有了SSH目录，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> ls -al的~/ .ssh</pre>
<p>
    <span style="font-size: 16px;">接着，生成新的SSH密钥，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> ssh-keygen -t rsa -C &quot;wengjiaojiao@outlook.com&quot;</pre>
<p>
    <span style="font-size: 16px;">(这里的email一定是你github的邮箱）</span>
</p>
<p>
    <span style="font-size: 16px;">这时候会出现这样一句话，建议是直接回车，保持默认设置，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> Enter file in which to save the key (/Users/wengjiaojiao/.ssh/id_rsa): [Press enter]</pre>
<p>
    <span style="font-size: 16px;">接着输入你的密码，并再确认一次即可，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> Enter passphrase (empty for no passphrase): [Type a passphrase]
 # Enter same passphrase again: [Type passphrase again]</pre>
<p>
    <span style="font-size: 16px;">这样你就会得到一个SSH key，就像这样的，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> Your identification has been saved in /Users/wengjiaojiao/.ssh/id_rsa.
 # Your public key has been saved in /Users/you/.ssh/id_rsa.pub.
 # The key fingerprint is:
 # 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db wengjiaojiao@outlook.com</pre>
<p>
    <span style="font-size: 16px;">然后配置ssh-agent，先要启用SSH代理，然后把SSH key 添加到 ssh-agent，这样才可以使用SSH key，</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> eval &quot;$(ssh-agent -s)&quot;
 ssh-add ~/.ssh/id_rsa</pre>
<p>
    <span style="font-size: 16px;">最后，把SSH key添加到你的账户里</span>
</p>
<pre class="brush:shell;toolbar: true; auto-links: false;"> sudo apt-get install xclip
 xclip -sel clip &lt; ~/.ssh/id_rsa.pub</pre>
<p>
    <span style="font-size: 16px;">打开github的settings设置，在SSH keys里添加 &nbsp;Add SSH key，这时候你会发现SSH Key在你的剪贴板里，把它放到Key里面就可以了。</span>
</p>
<p>
    <span style="font-size: 16px;">SSH Key不仅可以方便你不用重复输入，更能安全地管理你的文件。</span>
</p>
<hr/>
<p>
    <span style="font-size: 16px;">以上仅是我这两天接触的到git的皮毛，却也是受益良多。<span style="line-height: 22.5px; font-size: 16px;">写下这篇“初体验”，不仅是为了巩固这几天学到的内容，也希望在将来，忘了某个命令的我，可以多个解决问题的出口。</span></span>
</p>
<p>
    <br/>
</p>
