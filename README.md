# computer-config

## OS-X

Set up for a clean OS-X laptop.  I did not make a script as my
requirements vary.

- [shift it](https://github.com/fikovnik/ShiftIt),
[direct download](https://github-cloud.s3.amazonaws.com/releases/959084/72c0dcfa-ed3a-11e4-9d8e-cdafe2ee6e57.zip?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T032321Z&X-Amz-Expires=300&X-Amz-Signature=0e424ba996d4c7741aae86884b8347d77d521de04e91d432a40679c63695ee3f&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DShiftIt-1.6.3.zip&response-content-type=application%2Foctet-stream): Tool to move
windows side by side etc, similar to
WindowKey Left etc on Windows.
- [FlyCut](https://github.com/TermiT/Flycut/), [direct download](https://github-cloud.s3.amazonaws.com/releases/1502462/41c4d70e-88ad-11e6-8f6c-c51f67052c84.zip?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T032705Z&X-Amz-Expires=300&X-Amz-Signature=b167e10e4a3bfd6f873f73e805da7dc2ff5b34ad2ae7effd5ba44a067edc1ca7&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DFlycut.app.1.8.1.zip&response-content-type=application%2Foctet-stream) Cut and paste memory tool

```
Preferences
stickey bezel
launch flycut on login
```

- [Iterm2](https://iterm2.com/),  [direct download](https://iterm2.com/downloads/stable/iTerm2-3_0_10.zip) is a terminal replacement 

- [Aquamacs](http://aquamacs.org/), [direct download](https://github-cloud.s3.amazonaws.com/releases/163782/df98aa78-7ec1-11e6-94e2-f2baf22a8138.dmg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T033114Z&X-Amz-Expires=300&X-Amz-Signature=2852372ae195be018fcafa83540533b2ccf160788a97b283e5e356ea6a2dcb6a&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DAquamacs-Emacs-3.3.dmg&response-content-type=application%2Foctet-stream)

- install IntelliJ

- install brew 
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- brew install markdown
- brew install ruby
- brew install gem

- gem install compass
- brew install node
  need this version since it gives you access to npm, the node4 version does not have npm
- brew install joe

- npm -g install grunt-cli
- npm -g install karma
- npm -g install bower
- npm -g install phantomjs

go to the project directory (~/workspace/farmer-css)
- npm install
- bower install

install mongo
- brew install mongodb

- brew unlink node ( vice versa is brew link )
- brew install node `brew install homebrew/versions/node4-lts`

sample .gitconfig:
```
	[user]
		name = Addison Pan
		email = addisonp.work@gmail.com

	[alias]
	  co = checkout
	  ci = commit
	  st = status
	  hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
	  type = cat-file -t
	  dump = cat-file -p
	  lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
	  lola9 = log --graph --decorate --pretty=oneline --abbrev-commit --all -9
```

OS setup
System Preference -> Advanced -> Proxies -> click first 2 (Auto Proxy Discovery, Automatic Proxy Configuration)

bashit
installation directions: `https://github.com/Bash-it/bash-it`
```
$ . ~/.bash_profile
```

MONGO setup/requirements/start
```
sudo mkdir -p /data/db
sudo chmod 755 /data/db
sudo chown -R addison.pan: /data
mongod &
```
test with `mongo`

note: all bottle files that were downloaded
~/Libarary/Cache
