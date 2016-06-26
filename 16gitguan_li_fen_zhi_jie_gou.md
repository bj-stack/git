# 1.6Git管理分支结构

分支即是平行空间，假设你在为某个手机系统研发拍照功能，代码已经完成了80%，但如果将这不完整的代码直接提交到git仓库中，又有可能影响到其他人的工作，此时我们便可以在该软件的项目之上创建一个名叫“拍照功能”的分支，这种分支只会属于你自己，而其他人看不到，等代码编写完成后再与原来的项目主分支合并下即可，这样即能保证代码不丢失，又不影响其他人的工作。
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-05.png-bjstack" /></div><br/>
一般在实际的项目开发中，我们要尽量保证master分支是非常稳定的，仅用于发布新版本，平时不要随便直接修改里面的数据文件，而工作的时候则可以新建不同的工作分支，等到工作完成后在合并到master分支上面，所以团队的合作分支看起来会像上面图那样。
<div style="text-align: center;">
<img alt="" src="http://image.xuliangwei.com/git-06.png-bjstack" /></div>
<div class="text" style=" text-align:center;">图1-6 生产代码提交方式
</div> <br/>


