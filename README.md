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

Aquamacs is optional, for those that wish to use emacs:
- [Aquamacs](http://aquamacs.org/), [direct download](https://github-cloud.s3.amazonaws.com/releases/163782/df98aa78-7ec1-11e6-94e2-f2baf22a8138.dmg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAISTNZFOVBIJMK3TQ%2F20161017%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20161017T033114Z&X-Amz-Expires=300&X-Amz-Signature=2852372ae195be018fcafa83540533b2ccf160788a97b283e5e356ea6a2dcb6a&X-Amz-SignedHeaders=host&actor_id=0&response-content-disposition=attachment%3B%20filename%3DAquamacs-Emacs-3.3.dmg&response-content-type=application%2Foctet-stream)

- [Jiggler](http://www.sticksoftware.com/software/Jiggler.html), [direct download](http://downloads.sticksoftware.com/Jiggler.dmg)

- [Chrome](https://www.google.com/chrome/browser/desktop/index.html) / OS setup
	- (OS) System Preference -> Advanced -> Proxies -> click the 2nd option (Automatic Proxy Configuration)
OR
	- (Chrome) update proxy (upper right corner of the browser -> more -> setting -> advanced settings -> network)
```
DISABLE --> auto proxy discovery (DO NOT HAVE IT TURNED ON)
auto proxy configuration
```

DNS
```
21stcentury.com
pid.aig.com
```


- [Firefox](https://www.mozilla.org/en-US/firefox/new/), [direct download](https://www.mozilla.org/firefox/new/?scene=2)

- install IntelliJ (get it via an airdrop from someone who has the install package ie. `idealU-2016.2.4.dmg`)
	- plugins:
		- NodeJS
		- Karma
		- Line Sorter
		- Angular JS

- install brew via commandline in your iterm2
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install markdown
brew install ruby
brew install gem
gem install compass
brew install node
```
  need this version since it gives you access to npm, the node4 version does not have npm
```
brew install joe

npm -g install grunt-cli    
npm -g install karma
npm -g install bower
npm -g install phantomjs
```
Add `PHANTOMJS` to the class path 

Open the bash profile 
`vim ~/.bash_profile`

Add the following line in .bash_profile. Make sure  points to valid location. 

```
$ export PHANTOMJS_BIN=/usr/local/lib/node_modules/phantomjs/lib/phantom/bin/phantomjs
```
=====================

go to the project directory (~/workspace/farmer-css)
```
npm install (gets grunt and bower)
grunt update
```
optionally, get the node directory from a working machine and airdrop it to whomever needs it.
(could be in the /usr/local/Cellar directory)

if grunt update fails then try:
```
bower install
cd test/e2e
npm install
```
look for any errors such as the following example
```
> node node_modules/protractor/bin/webdriver-manager update

events.js:141
      throw er; // Unhandled 'error' event
      ^

Error: unable to get local issuer certificate
    at Error (native)
    at TLSSocket.<anonymous> (_tls_wrap.js:1022:38)
    at emitNone (events.js:67:13)
    at TLSSocket.emit (events.js:166:7)
    at TLSSocket._init.ssl.onclienthello.ssl.oncertcb.TLSSocket._finishInit (_tls_wrap.js:586:8)
    at TLSWrap.ssl.onclienthello.ssl.oncertcb.ssl.onnewsession.ssl.onhandshakedone (_tls_wrap.js:428:38)

npm ERR! Darwin 15.6.0
npm ERR! argv "/usr/local/Cellar/node4-lts/4.6.0/bin/node" "/usr/local/bin/npm" "install"
npm ERR! node v4.6.0
npm ERR! npm  v2.15.9
npm ERR! code ELIFECYCLE
npm ERR! @ install: `node node_modules/protractor/bin/webdriver-manager update`
npm ERR! Exit status 1
npm ERR!
```
or go to starbucks and rerun `grunt update` in the farmers-css directory


install mongo
```
brew install mongodb
```

MONGO setup/requirements/start
```
sudo mkdir -p /data/db
sudo chmod 755 /data/db
sudo chown -R addison.pan: /data
mongod &
```
test with `mongo`

brew unlink node ( vice versa is brew link node4-lts)
brew install an older version of node `brew install homebrew/versions/node4-lts`

- node updates


sample ~/.git-authors
```
authors:
  jl: Joey Leung
  bk: Ben Kamysz
  ap: Addison Pan
  hs: Harshesh Shah
  mh: Manuk Hovanesian
  wl: William Lee
  im: Isaac Mahgrefteh

email_addresses:
  jl: xxxx@farmersinsurance.com
  bk: xxx@farmersinsurance.com
  ap: xxx@farmersinsurance.com
  hs: xxx@capgemini.com
  mh: xxx@farmersinsurance.com
  wl: xxx@farmersinsurance.com
  im: xxx@farmersinsurance.com
```
sample ~/.gitconfig:
```
    [user]
        name = Addison Pan
        email = haha@hehe.there

    [alias]
      co = checkout
      ci = commit
      st = status
      hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
      type = cat-file -t
      dump = cat-file -p
      lola = log --graph --decorate --pretty=oneline --abbrev-commit --all
      lola9 = log --graph --decorate --pretty=oneline --abbrev-commit -n9
      cb = rev-parse --abbrev-ref HEAD
      dci = duet-commit
      pl = pull --ff-only
      unpushed = log --branches --not --remotes --simplify-by-decoration --decorate --oneline
      ready = rebase -i @{u}
      lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%C(bold blue)<%an>%Creset' --abbrev-commit
      story = "!f() { n=$1; story=$(sed -e \"s/#//\" <<< $n); branch=$(git branch -a | grep -o \"$story[-_a-zA-Z]*\" | head -n 1); git checkout $branch; }; f"

    [core]
      editor = /usr/bin/nano
      excludesfile = /Users/addison.pan/.gitignore_global
      autocrlf = input

    [difftool "sourcetree"]
      cmd = opendiff \"$LOCAL\" \"$REMOTE\"
      path =
    [mergetool "sourcetree"]
      cmd = /Users/addison.pan/Applications/SourceTree.app/Contents/Resources/opendiff-w.sh \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
      trustExitCode = true
    [mergetool "bc3"]
      cmd = \"/Users/addison.pan/Applications/Beyond Compare.app/Contents/MacOS/bcomp\"  \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
      trustExitCode = true

    [merge]
      tool=bc3
```

bashit
installation directions: `https://github.com/Bash-it/bash-it`
```
$ . ~/.bash_profile
```




- need to install ant 'brew install ant'
	- require java 'brew cask install java'
- need to install selenium



for remote pairing:
screen hero
	- request an invite from a member who already has an account

note: all bottle files that were downloaded
~/Libarary/Cache

Airdrop - visible hostname
```
scutil --set HostName
```
or go to system preferences -> sharing -> change your computer name


Git Duet Wrapper
```
brew tap git-duet/tap
brew install git-duet
```
Then use the git duet wrapper by setting it up as the git executable in intelliJ.  The git duet wrapper is under scripts/intellij_git_duet_wrapper.sh
```
in intelliJ menu -> command ,
git -> path to executable -> find your copy of the script
```
Create the link to precommit hook
```
ln -s $PWD/scripts/precommit_hook.sh .git/hooks/pre-commit
```
setup the git proxy through ssh
```
ssh-keygen -t rsa -b 4096 -C "xxx"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub  (copy this)
```
then go to github.com -> settings -> SSH and GPG keys -> new SSH Key -> put in the data copied above from the id_rsa.pub

verify that the git remote is through ssh not through https
```
git remote -v
```

if the git remote is through https then change it via
```
git remote set-url origin git@github.com:USERNAME/OTHERREPOSITORY.git (get the actual value from a team member)
```
/etc/hosts for Jenkins
```
xx.xx.xx.xx css-jenkins-local css-jenkins
```
note: cannot reach jenkins via guestnet

Install the post receive hook (verify that you have css-jenkins in the hosts file)
```
ln -s $PWD/scripts/postreceive_hook.sh .git/hooks/post-receive
```

VPN with a MAC
could try:
1. remove all proxy information and uncheck the `Use Passive FTP Mode (PASV)`
2. remove all DNS Search Domains

noticed that VPN with MAC out of the office works best when directly wired in and not using the wireless

Maven:
create a file settings.xml in the ~/.m2 directory, an example is listed below, please contact Addison or Ben for more details

```
<settings> 
  <proxies>
   <proxy>
      <id>xxx</id>
      <active>true</active>
      <protocol>http</protocol>
      <host>xxx</host>
      <port>xxx</port>
    </proxy>
  </proxies>
</settings>
```

Ask Dirk:

2. when silver is pushed to the remote repository, what is the trigger to sf push to the development environments

TO DO:
setup proxies for npm and grunt
