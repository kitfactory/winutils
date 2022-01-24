# winutils
Windows binaries for the Hadoop version

These are built directly from the same git commits that were used to create the official ASF release.
The winutils binary of [cdarlint/winutils](https://github.com/cdarlint/winutils)  is not compatible with my Windows 11 environment. I have rebuilt winutils for the  Windows11 x64.


-----------------------------------------------------

# winutils
Hadoop版用Windowsバイナリ

## このリポジトリについて
Windows上でSparkを動作させるにはwinutilsが必要となります。このリポジトリのwinutilsは、ASFの公式リリースを作成するために使用されたのと同じgitコミットから直接ビルドされたものです。

現在、[cdarlint/winutils]()のwinutilsバイナリは、私のWindows 11環境と互換性がありませんでしたので、Windows11 x64用にwinutilsをリビルドしました。

ビルド手順は以下を参考にしています。ありがとう。
https://pivotalbi.com/build-your-own-winutils-for-spark/

## Windows11 Spark環境の構築
## 準備：Javaのインストール

Java8をインストールし、環境変数 JAVA_HOMEを設定してください。
例
set JAVA_HOME=C:\Java8\jre

## 準備：再配布パッケージのインストール

もし、Visual Studio 再配布パッケージがインストールされていない場合は、以下からダウンロードしてください。

https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2015-2017-2019-and-2022


##　Hadoop

以下よりHadoopのバイナリをダウンロードします。
https://hadoop.apache.org/releases.html

ダウンロード

### SPARK_HOMEの設定

環境変数HADOOP_HOMEを本環境を設定してください。

例
set HADOOP_HOME=C:\Users\foo\workspace\winutils\hadoop-3.3.2rc5

## Pathの設定
HADOOP_HOME\binを環境変数Pathに追加してください。

例
set PATH=%PATH%;HADOOP_HOME\bin

### SPARK_DIST_CLASSPATHの設定


## winutilsの設定
このリポジトリをダウンロードし、%HADOOP_HOME%\binにこのリポジトリのbinの内容をコピーします。


# Sparkのインストール

Sparkのダウンロードサイトから、Pre-build with user provided hadoopをダウンロードします。(Spark 3.1.2ではテストしています)
https://spark.apache.org/downloads.html

# SPARK_HOMEの設定

