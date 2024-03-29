如何将Ubuntu14.04安全的升级到14.10
================================================================================
本文将讨论如何将Ubuntu14.04升级到14.10的beta版。Ubuntu14.10的最终beta版已经发布了

如果想从Ubuntu14.04/13.10/13.04/12.10/12.04或者更老的版本升级到14.10，只要遵循下面给出的步骤。注意，你不能直接从13.10升级到14.10。你应该想将13.10升级到14.04在从14.04升级到14.10。下面是详细步骤。

下面的步骤不仅能用于14.10，也兼容于一些像Lubuntu14.10，Kubuntu14.10和Xubuntu14.10等的Ubuntu衍生版本

**重要**：在升级之前，保险起见，不要忘了将你的数据在U盘或外部硬盘上保存一下。

### 桌面升级 ###

在升级之前，我们要先更新系统。打开终端输入以下命令

    sudo apt-get update && sudo apt-get dist-upgrade

上面的命令会下载安装最新的包。

重启你的电脑以完成更新。

然后输入下面的命令来升级到新的可获得的版本

    sudo update-manager -d

软件更新器会出现并且搜索新的发行版。

After a few seconds, you will see a screen like below that saying: “**However, Ubuntu 14.10 is available now (you have 14.04)**”. Click on the button Upgrade to start upgrading to Ubuntu 14.10.


![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Software-Updater_001.png)

The Software Updater will ask you to confirm still you want to upgrade. Click Start Upgrade to begin installing Ubuntu 14.10.

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Release-Notes_002.png)

**Please Note**: This is a beta release. Do not install it on production systems. The final stable version will be released in a couple of hours.

Now, the Software Updater will prepare to start setting up new software channels.

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Distribution-Upgrade_003.png)

After a few minutes, the software updater will notify you the details the number of packages are going to be removed, and number of packages are going to be installed. Click **Start upgrade** to continue. Make sure you have good and stable Internet connection.

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Untitled-window_004.png)

Now, the updater will start to getting new packages. It will take a while depending upon your Internet connection speed.

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Distribution-Upgrade_005.png)

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Distribution-Upgrade_001.png)

After a while, you’ll be asked to remove unnecessary applications. Finally, click **Restart** to complete the upgrade.

Congratulations! Now, you have successfully upgraded to Ubuntu 14.10.

![](http://180016988.r.cdn77.net/wp-content/uploads/2014/10/Details_002.png)

That’s it.. Start using the new Ubuntu version.

### Server Upgrade ###

To upgrade from Ubuntu 14.04 server to Ubuntu 14.10 server, do the following steps.

Install the update-manager-core package if it is not already installed:

    sudo apt-get install update-manager-core

Edit the file /etc/update-manager/release-upgrades,

    sudo nano /etc/update-manager/release-upgrades

and set Prompt=normal or Prompt=lts as shown below.

    # Default behavior for the release upgrader.
    
    [DEFAULT]
    # Default prompting behavior, valid options:
    #
    #  never  - Never check for a new release.
    #  normal - Check to see if a new release is available.  If more than one new
    #           release is found, the release upgrader will attempt to upgrade to
    #           the release that immediately succeeds the currently-running
    #           release.
    #  lts    - Check to see if a new LTS release is available.  The upgrader
    #           will attempt to upgrade to the first LTS release available after
    #           the currently-running one.  Note that this option should not be
    #           used if the currently-running release is not itself an LTS
    #           release, since in that case the upgrader won't be able to
    #           determine if a newer release is available.
    Prompt=normal

Now, it is time to upgrade your server system to latest version using the following command:

    sudo do-release-upgrade -d

Follow the on-screen instructions. You’re done!!.

Cheers!!

--------------------------------------------------------------------------------

via: http://www.unixmen.com/upgrade-ubuntu-14-04-trusty-ubuntu-14-10-utopic/

作者：SK
译者：[译者ID](https://github.com/译者ID)
校对：[校对者ID](https://github.com/校对者ID)

本文由 [LCTT](https://github.com/LCTT/TranslateProject) 原创翻译，[Linux中国](http://linux.cn/) 荣誉推出

[1]:https://wiki.ubuntu.com/UtopicUnicorn/ReleaseSchedule
