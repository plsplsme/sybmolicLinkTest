# sybmolicLinkTest
To test symbolic link to share program within Git.

# Conclusion

It works on linux. Not on Windows (Shoot!).

## How I created the project

```bash
#prepare
> git init
> git add remote origin ***

#create project
> mkdir project
> cd project
> mkdir admin
> mkdir user

#create file to share
> cd admin
> mkdir public
> echo 'test1' > public/test1.txt
> echo 'test2' > public/test2.txt

#create symbolic link
> cd ../user
> ln -s ../admin/public public
> cd ..

# git push
> git add .
> git commit -m "add"
> git push origin master
```

## Git clone in another linux server

```bash
> git init
> git clone ***

> ls -la /user/publi> c
lrwxrwxrwx 1 user user 15 Dec 11 09:31 public -> ../admin/public
```

It works!

## Git cline in another Windows Server

```
> git init
> git clone ***

> notepad user/public
```

user/public is just a text like following.

```txt
../admin/public
```





