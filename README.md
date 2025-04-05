usage:

1. We first pull down the "https://github.com/zzhang154/ndnSIM-2.9-raw/tree/ndnSIM-ns-3.35" into the project file, i.e., ./ndnSIM-2.9

Then we have the folder ndnSIM-2.9. But now, we only pull the files of ns-3 related, and since the limitation of git-ignore. We have to pull the ndnSIM file independently.

2. delete the git submodule in ndnSIM file
Step 1: First, remove the nested git repository from the index
git rm --cached src/ndnSIM/ndn_app

Step 2: Remove the .git directory from ndn_app
rm -rf src/ndnSIM/ndn_app/.git

Step 3: Now add the ndn_app directory as regular file
git add src/ndnSIM/ndn_app

3. git pull the ndnSIM-2.9 from the link "https://github.com/zzhang154/ndnSIM-2.9-raw/tree/main".

if the pull process has question, just use:
wget https://github.com/zzhang154/ndnSIM-2.9-raw/archive/refs/heads/master.zip
unzip master.zip
mv ndnSIM-2.9-raw-master ndnSIM

4. optimized mode.
./waf configure --disable-python --enable-example -d optimize

5. run mode
NS_LOG=ndn.Consumer:ndn.Producer ./waf --run=ndn-grid
./waf --run=ndn-grid

ndnSIM
======

ndnSIM

- 模拟代码目录 : /examples

- 转发器陌路 : /NFD

---------------------------------------------
### ndnSim 官方说明

A new release of [NS-3 based Named Data Networking (NDN) simulator](http://ndnsim.net/)
went through extensive refactoring and rewriting.  The key new features of the new
version:

- [NDN Packet Specification](http://named-data.net/doc/NDN-packet-spec/current/)

- ndnSIM uses implementation of basic NDN primitives from
  [ndn-cxx library (NDN C++ library with eXperimental eXtensions)](http://named-data.net/doc/ndn-cxx/)

  Based on version `0.7.0`

- All NDN forwarding and management is implemented directly using source code of
  [Named Data Networking Forwarding Daemon (NFD)](http://named-data.net/doc/NFD/)

  Based on version `0.7.0`

- Allows [simulation of real applications](http://ndnsim.net/guide-to-simulate-real-apps.html)
  written against ndn-cxx library

- Requires a modified version of NS-3 based on version `ns-3.30.1`

[ndnSIM documentation](http://ndnsim.net)
---------------------------------------------

For more information, including downloading and compilation instruction, please refer to
http://ndnsim.net or documentation in `docs/` folder.
