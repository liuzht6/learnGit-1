# Git basic instructions

��ǩ���ո�ָ����� Git learing

---

###�������ع�����
a.` mkdir dirname`
b.` cd dirname` ���������git���ܹ������Ŀ�
c.` git init`
```
Initialized empty Git repository in /Users/Perdon/Documents/Programme-Preparation/learngit/.git/
```
 ʹ��` ls -ah`���Բ鿴��Ŀ¼�����ص�.git�ļ���������¼����git
###���ļ��ӱ��ع��������ӵ����ذ汾��
#####�Ƚ��ļ��ӿɼ��Ĺ��������ӵ�.git���������ݴ���(stage)
a. ` git add filename`
���ļ���.git�������ݴ���(stage)���ӵ�.gitΪ�����Զ������ĵ�һ����֧master
ע�⣺����add����ļ�����һ���Խ���commit
b.` git commit -m ����־��Ϣ��`
```
[master (root-commit) 81905ae] empty
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.txt
```
��������ʾ������commitһ���޸���1���ļ���һ����0�����Ӻ�0�����٣�
#####�����ذ汾���ļ����ӵ�Զ�̿�
a.�����û���Ŀ¼��ע�ⲻ�Ǳ�Ŀ¼����Macbook-Perdon:~ Perdon$Ŀ¼�¿���û��id_rsa��id_rsa.pub�������ļ�������������bֱ�ӽ���c��
b.��ȡ��ĵ��Զ��е�SSH KEY:
` ssh-keygen -t rsa -C "***@qq.com"`
c.��½GitHub���򿪡�Account settings������SSH Keys��ҳ�棺
Ȼ�󣬵㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ�������
d.�������ض��Ĳֿ��Github���´��Ĳֿ���й���
�ڱ��زֿ������һ�����
`git remote add origin git@github.com:yourGithubusername/Github�ֿ���.git`
e.��һ�ΰѱ��ذ汾������������Ƶ�Զ�̿�
origin:Զ�̿�		master:���ذ汾��ķ�֧
` git push -u origin master`
֮����Ҫ�޸ĵĻ�ʹ�ã�
` git push origin master`
#####���ļ���GithubԶ�̿����ӵ����ع�����
` git clone git@github.com:yourGithubusername/Github�ֿ���.git`

---


##��������ָ��
###�鿴��ǰ�汾���������
- ` git status`
```
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#    modified:   readme.txt
```
`# modified:   readme.txt`
����˵�����������ļ�readme.txt�иı�
`# Changes not staged for commit`
����˵��û���ļ���add���ݴ���



` git status`
```
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       modified:   readme.txt
```
`# Changes to be committed`
����˵���Ѿ����ļ�add���ݴ���������û�н���commit



` git status`
```
# On branch master
nothing to commit (working directory clean)
```
˵���������ݴ������ļ����Ѿ�commit����֧���ݴ���Ϊ��

###�鿴�����޸����
- ` git diff filename`
```
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```
###�鿴��ʷ��¼
- ` git log --pretty=oneline`
```
3628164fb26d48395383f8f31179f24e0882e1e0 append GPL
ea34578d5496d7dd233c827ed32a8cd576c5ee85 add distributed
cb926e7ea50ad11b8f9e909c05226233bf755030 wrote a readme file
```
###���в�ͬ�汾��ѡ��
- ` git reset --hard commit_id`
������һ���汾��
` git reset --hard HEAD^`
���������100���汾
` git reset --hard HEAD~100`

###�����޸�
a.�������������޸ģ���ʵ���ǽ����°汾����ļ�������������
` git checkout -- filename`
b.�����ݴ������޸ģ�
���ݴ������޸Ļ��˵�������
HEAD:���°汾
` git reset HEAD filename`
�ٳ������������޸ģ�
` git checkout -- filename`
c.�����汾����޸�
ʹ�û��˵���һ���汾�ķ���

###ɾ���ļ�
a.ɾ���������ļ�
` rm filename`
b.ɾ���汾���ļ�
` git rm filename`
c.ɾ���������ļ���Ҫ��ԭ��
` git checkout -- filename`
d.ɾ��Github������ļ�
` git commit -a -m "A file was deleted"`
` git push origin master`




