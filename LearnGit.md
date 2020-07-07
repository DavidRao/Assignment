# 1. 克隆并新建分支

1. `git clone` 克隆项目
2. `git branch` 新建分支，（用你的名字的拼音写法命名该分支，全小写，如：raozhanwei）
3. `git checkout` 切换到你新建的分支

# 2. 理解工作区、暂存区、本地版本库

2. - 新建文件`letter.txt`
   - `git add letter.txt`
   - `git status`观察
   - `git rm --cached letter.txt`
   - `git status`观察
2. - 将`letter.txt`提交到本地版本库
3. - 新建`number.txt`、`fruit.txt`、`animal.txt`，如何用最少的指令，一次性提交到版本库？
   - 答：git add ...... 然后git commi -m "..." .....
4. - `fruit.txt`、`animal.txt`中分别添加一种水果、一种动物，如何用最少的指令全部添加到暂存区？
   - 在上面的基础上，如何用最少的指令提交到版本库？
   - 答：可用git add fruit.txt animal.txt ...一次添加多个，然后用git commit -m "..." fruit.txt animal.txt number.txt 同时提交多个
5. - `fruit.txt`、`animal.txt`中再分别添加一种水果、一种动物，如何用最少的指令全部提交到版本库？
   - 答：
6. - 说说`git commit --amend`的作用，可以用上面的文件做例子说明
   - 答：
7. - 综合上面的多种方法，向`letter.txt`中逐行添加a, b, c, d, e, f, g，一行一个，不要一次性加完，重在练习
   - 同理向`number.txt`中逐行添加1, 2, 3, 4, 5, 6
8. - 综合使用`git log`的四种显示方式，观察
   - 截图其中一种：

# 3. 版本前进、回退

这里关于reset的操作只要求掌握`--hard`的用法

1. - `letter.txt`回退到插入字母a时候的版本，`number.txt`回退到插入1时候的版本（使用checkout）
   - 使用`git log`简略显示的三种方法，观察并说说区别
   - 答：
2. - 如何前进到a, b, c, d, e, f, g齐全，1, 2, 3, 4, 5, 6齐全的版本（使用reset）
   - 完成后用你喜欢的log方式截图：
3. - `letter.txt`回退到插入字母 e 时候的版本，`number.txt`回退到插入3时候的版本（使用checkout）
   - 完成后用你喜欢的log方式截图：

# 4. 理解删除

删除在git的版本库中只是一条历史记录，文件在版本库中仍然存在，所以可以随时通过版本控制找回删除的文件

1. - `git branch temp` 新建 temp 分支
   - `git checkout temp` 转到 temp 分支

2. - `rm fruit.txt`
   - `git status` 观察
   - 将删除记录提交到版本库
3. - `git rm animal.txt`
   - `git status` 观察
   - 将删除记录提交到版本库

4. - 使用前面的版本回退方法，将`fruit.txt`找回
   - 在文件夹中右键`fruit.txt`，删除
   - `git status` 观察
   - 将删除记录提交到版本库
5. - 使用前面的版本回退方法，将`animal.txt`找回
   - `git mv animal.txt tiger.txt`
   - `git status` 观察
   - 将重命名记录提交到版本库
6. - 右键`tiger.txt`，重命名为`animal.txt`
   - `git status` 观察
   - 将重命名记录提交到版本库

# 5. checkout的另一用法

1. 使用前面介绍的任一种方法删除`animal.txt`

2. 修改`letter.txt`中的内容为（你的名字是指填写你的真实名字，到后面“解决冲突”部分有用）

   ```
   e edit by 你的名字
   d edit by 你的名字
   c edit by 你的名字
   b edit by 你的名字
   a edit by 你的名字
   ```

3. 修改`number.txt`中的内容为（你的名字是指填写你的真实名字，到后面“解决冲突”部分有用）

   ```
   3 edit by 你的名字
   2 edit by 你的名字
   1 edit by 你的名字
   ```

4. 提交到版本库

5. - `git checkout 以你名字命名的分支名`，回到你的名字为命名的分支
   - `git checkout temp -- letter.txt`
   - `git checkout temp -- animal.txt`
   - 观察`letter.txt`、`animal.txt`的内容
   - `git checkout 以你名字命名的分支名 -- letter.txt`
   - `git checkout 以你名字命名的分支名 -- animal.txt`
   - 观察`letter.txt`、`animal.txt`的内容
   - `git checkout temp -- letter.txt`
   - `git checkout temp -- animal.txt`
   - 提交到版本库

这个操作可以把不同分支的同名文件进行变换。具体是把指定分支的版本库中HEAD指向的版本的同名文件，覆盖当前分支的同名文件



# 6. 合并与解决本地冲突

1. - `git merge temp`
   - 观察此时的命令行提示
2. - 解决本地冲突，文件最终的样子修改为
   - ```
     e edit by 你的名字
     d edit by 你的名字
     c edit by 你的名字
     b edit by 你的名字
     a edit by 你的名字
     ```
   - ```
     3 edit by 你的名字
     2 edit by 你的名字
     1 edit by 你的名字
     ```

3. 提交到版本库

执行效果最终效果虽然与上面的`checkout`一样，但它们实现的方式是不同的。从功能上来说，`merge`是不能对指定文件操作的，而且被合并的支路会变得和合并过来的支路的文件结构一模一样，如果两条支路的差异很多，这个操作需要谨慎。而`checkout`则可以

# 7. 合并分支

1. 把以你名字命名的分支名合并到copy分支



# 8. push到远程库









