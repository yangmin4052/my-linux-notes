```bash
cd ~
vim .bashrc
# 将
function git_branch {
branch="`git branch 2>/dev/null | grep "^\*" | sed -e "s/^\*\ //"`"
if [ "${branch}" != "" ];then
if [ "${branch}" = "(no branch)" ];then
branch="(`git rev-parse --short HEAD`...)"
fi
echo " ($branch)"
fi
}

export PS1='[\u@\h \[\033[01;34m\]\W\[\033[00m\]]\[\033[01;32m\]$(git_branch)\[\033[00m\] \$ '

# 放置于文末
# 保存退出
source ./.bashrc
```
