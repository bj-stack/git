# 1.1Git诞生历史
我想大家还记得Linus torvalds在1991年时发布了Linux操作系统吧，从那以后Linux系统变不断发展壮大，因为Linux系统开源的特性，所以一直接受着来自全球Linux技术爱好者的贡献，志愿者们通过邮件向Linus发送着自己编写的源代码文件，然后由Linus本人通过手工的方式将代码合并，但这样不仅没有效率，而且真的是太痛苦了。

一直到2002年，Linux系统经过十余年的不断发展，代码库已经庞大到无法再让Linus通过手工的方式管理了，但是Linus真的很不喜欢CVS或者Subversion版本控制系统，于是商业公司BitMover决定将其公司的BitKeeper分布式版本控制系统授权给Linux开发社区来免费使用，当时的BitKeeper可以比较文件内容的不同，还能够将出错的文档还原到历史某个状态，Linus终于放下了心里的石头。 
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-01.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-1 分布式版本控制流程图</div> <br/>

CVS和Subversion属于传统的版本控制系统，而分布式版本控制系统最大的特点是不需要每次提交都把文件推送到版本控制服务器，而是采用分布式版本库的机制，使得每个开发人员都够从服务器中克隆一份完整的版本库到自己计算机本地，不必再完全依赖于版本控制服务器，使得源代码的发布和合并更加方便，并且因为数据都在自己本地，不仅效率提高了，而且即便我们离开了网络依然可以执行提交文件、查看历史版本记录、创建分支等等操作，真的是开发者的福音啊。

就这样平静的度过了三年时间，但是Linux社区聚集着太多的黑客人物，2005年时，那位曾经开发Samba服务程序的Andrew因为试图破解BitKeeper软件协议而激怒了BitMover公司，当即决定不再向Linux社区提供免费的软件授权了，此时的Linus其实也早已有自己编写分布式版本控制系统的打算了，于是便用C语言花了2周创建了Git分布式版本控制系统，并上传了Linux系统的源代码。
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-02.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-2 git_log</div> <br/>
Git不仅是一款开源的分布式版本控制系统，而且有其独特的功能特性，例如大多数的分布式版本控制系统只会记录每次文件的变化，说白了就是只会关心文件的内容变化差异，而Git则是关注于文件数据整体的变化，直接会将文件提交时的数据保存成快照，而非仅记录差异内容，并且使用SHA-1加密算法保证数据的完整性。

Git为了提高效率，对于没有被修改的文件，则不会重复存储，而是创建一个链接指向之前存储过的文件。
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-03.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-3 git提交流程图</div><br/>
在正式使用前，我们还需要弄清楚Git的三种重要模式，分别是已提交、已修改、已暂存

已提交(committed):表示数据文件已经顺利提交到Git数据库中。

已修改(modified):表示数据文件已经被修改，但未被保存到Git数据库中。

已暂存(staged):表示数据文件已经被修改，并会在下次提交时提交到Git数据库中。

提交前的数据文件可能会被随意修改或丢失，但只要把文件快照顺利提交到Git数据库中，那就可以完全放心了，流程为：

1.在工作目录中修改数据文件。

2.将文件的快照放入暂存区域。

3.将暂存区域的文件快照提交到Git仓库中。

<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-04.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-4 git工作模式</div>