# git pushをしたらrejectされてしまいできなかった

## error文
error: failed to push some refs to 'https://github.com/suzuki-yuka-27/net_shopping_size.git'  
hint: Updates were rejected because the remote contains work that you do  
hint: not have locally. This is usually caused by another repository pushing  
hint: to the same ref. You may want to first integrate the remote changes  
hint: (e.g., 'git pull ...') before pushing again.  
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

## 原因
上記によると、リモートリポジトリとローカルリポジトリで内容が違うようだ。  
この作業をする前に、ER図をURLで見れるようにする方法が分からず、ファイルでリモートリポジトリへ直接ER図をcommitし、pull requestを作成した。  
その後、URLでER図を見る方法が分かったため、ローカル（VScode）でER図のファイルを削除した。  
つまり、ローカルとリモートで別々の作業をしてしまっていたために起きてしまったエラーだった。  

## 解決方法
git pullコマンドでリモートリポジトリとローカルリポジトリを最新の状態でマージすることで、再びgit pushできるようになった。