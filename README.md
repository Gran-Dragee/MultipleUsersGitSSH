# MultipleUsersGitSSH

##### ssh鍵の作成

```
$ cd ~/.ssh
$ ssh-keygen -t rsa -C "user1@..."
$ ssh-keygen -t rsa -C "user2@..."
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

