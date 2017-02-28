# MultipleUsersGitSSH

##### ssh鍵の作成

```
$ cd ~/.ssh
$ ssh-keygen -t rsa -C "user1@gmail.com"
$ ssh-keygen -t rsa -C "user2@gmail.com"
```

##### configファイルの作成

```
$ vim ~/.ssh/config
		Host github.com-User1
		    HostName github.com
		    User git
		    Port 22
		    IdentityFile ~/.ssh/user1

		Host github.com-User2
		    HostName github.com
		    User git
		    Port 22
		    IdentityFile ~/.ssh/user2
```

##### keyの登録

user1, user2の鍵をそれぞれのユーザーのgithubに登録。  

##### 接続テスト

```
$ ssh -T git@github.com-User1
$ ssh -T git@github.com-User2
```

##### sshユーザーを指定してclone

```
$ git clone git@github.com-User1:User1/Project.git
$ git clone git@github.com-User2:User2/Project.git
```

これで好きなようにpush等が可能になります。  
