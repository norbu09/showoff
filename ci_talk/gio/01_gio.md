!SLIDE 
# Giovanni #

!SLIDE full-page

![capistrano](capistrano.jpg)

!SLIDE commandline incremental
    
    @@@ sh
    $ gio deploy
    Running deploy for 'githublicious'
    Loading git Plugin
    [git] Tag: [v1331523346] 
    [bender] connected
    [bender] running update_cache
    From github.com:norbu09/githublicious
       db1629a..34c2176  master     -> origin/master
    [bender] Fetching origin
    Fetching origin
    Updating db1629a..34c2176
    Fast-forward
     Mojolicious/Plugin/Jenkins.pm |    5 +++--
     1 files changed, 3 insertions(+), 2 deletions(-)
    [bender] running restart


!SLIDE commandline incremental

    @@@ sh
    $ cat .giovanni.conf
    [project "githublicious"]
        hosts = bender
        root = ~/githublicious
        init     = ~/githublicious/restart
        deploy   = update_cache, restart
        rollback = rollback, restart
        repo = git@github.com:norbu09/githublicious.git
        user = lenz

!SLIDE
# deployment the perl way #

all plugin based

extend it to your hearts contend

!SLIDE
# fork it on github #

https://github.com/norbu09/Giovanni

!SLIDE
# more complex example #

!SLIDE commandline incremental

    @@@ sh
    $ cat iwmn.gio
    [project "iwmn"]
    hosts    = hugo, hn
    root     = /usr/local/d8o/iwmn
    init     = /etc/init.d/iwmn
    deploy   = update_cache, rollout_timestamped, restart_phased, notify
    rollback = rollback_timestamped, restart_phased, notify
    repo     = git@github.com/ideegeo/iwmn-base.git
    cache    = /usr/local/d8o/git
    user     = deploy
    jabber_user = XXXXXXXXXXXX
    jabber_pass = XXXXXXXXXXXX
    jabber_to   = room, user, ...

!SLIDE bullets
# gio supports #

* git
* jabber notify
* timestamped and traditional rollout
* rollback
* restart

!SLIDE bullets
# summary #

* automate everything
* notify a lot
* extend the stuff we already built

!SLIDE
# thanks #
## @norbu09 ##


!SLIDE smbullets
# credits #

    /images
        + http://flickr.com/
        +-- pmeidinger
        + wikipedia
