# CocoaPods多版本共存及切换

#### Ruby、RVM、Gem、CocoaPods的关系

* 名词解释

  * **Ruby**，一种开发语言，不细说。
  * **RVM**，全名Ruby Version Management，安装不同版本的Ruby以及切换某个版本为当前使用版本。
  * **Gem**，全名RubyGems，用Ruby写的用于管理Ruby第三方库的命令行工具，在命令行里我们习惯叫它gem。它隶属于某个版本的Ruby，即，不同的Ruby版本都各自有对应版本的Gem。
  * **CocoaPods**，众多Gem第三方库中的一个，具体做什么的就不说了。我们可以使用Gem安装指定版本的CocoaPods: **gem install cocoapods -v 0.38.2 或 gem install cocoapods -v 1.0.0**。

* 关系：所以，可以安装多个版本的Ruby，每个版本的Ruby都有一个Gem工具，使用Gem可以安装指定版本的CocoaPods。

#### 安装多个版本的Cocoapds及切换

* 原理概述：通过了解上面的关系，我们可以在不同版本Ruby下，通过Gem安装某一个版本的CocoaPods，然后通过用切换Ruby版本来达到切换不同版本CocoaPods的目的。

* 安装：

  * 安装ruby 2.2.2、2.3.3\(已装请忽略\)

    * ruby 2.2.2环境下安装cocoapods 0.38.2

    * ruby 2.3.3环境下安装cocoapods 1.0.0

  * 安装RVM\(已装请忽略\):

    ```bash
    # 可能需要翻墙
    $ curl -L get.rvm.io \| bash -s stable

    #要想使用 'rvm'命令需要执行下面一行代码
    $ source ~/.rvm/scripts/rvm
    ```

  * 安装Ruby\(2.2.2\)和CocoaPods\(0.38.2\)

    ```bash
      # 列表已安装的ruby版本
      $ rvm list
  
      # 列出可安装的ruby版本
      $ rvm list known
    ```




        \# 安装ruby 2.2.2

        $ rvm install 2.2.2



        \# 切换ruby版本到2.2.2，确保是使用的刚安装的ruby版本

        $ rmv use 2.2.2



        \# 查看ruby环境信息，确保已切到ruby 2.2.2

        $ gem environment



        \# 安装CocoaPods 0.38.2

        $ gem install cocoapods -v 0.38.2



        \# 查看CocoaPods版本信息，cocoapods版本信息应该显示为0.38.2

        $ pod --version





    \`\`\`



    \* 安装Ruby\(2.3.3\)和CocoaPods\(1.0.0\)



    \`\`\`shell

        \# 列表已安装的ruby版本

        $ rvm list



        \# 列出可安装的ruby版本

        $ rvm list known



        \# 安装ruby 2.3.3

        $ rvm install 2.3.3



        \# 切换ruby版本到2.3.3，确保是使用的刚安装的ruby版本

        $ rmv use 2.3.3



        \# 查看ruby环境信息，确保已切到ruby 2.3.3

        $ gem environment



        \# 安装CocoaPods 1.0.0

        $ gem install cocoapods -v 1.0.0



        \# 查看CocoaPods版本信息，cocoapods版本信息应该显示为1.0.0

        $ pod --version



    \`\`\`



    \* 切换



    \`\`\`shell

        \# 使用0.38.2版本CocoaPods

        $ rvm use 2.2.2



        \# 使用1.0.0版本CocoaPods

        $ rvm use 2.3.3

    \`\`\`

#### 后续

* 欢迎大家提出更优的方案

* 上面的方案有些繁琐，目前能用，后续考虑封装成shell文件



