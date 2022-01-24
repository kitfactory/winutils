# winutils
Windows binaries for the Hadoop version

These are built directly from the same git commits that were used to create the official ASF release.
The winutils binary of [cdarlint/winutils](https://github.com/cdarlint/winutils)  is not compatible with my Windows 11 environment. I have rebuilt winutils for the  Windows11 x64.


------------------------------------------

# winutils
Windows binaries for Hadoop version

## 1. About this repository
In order to run Spark on Windows, you need winutils. The winutils in this repository are built directly from the same git commits that were used to create the official ASF release.

Currently, the winutils binary in [cdarlint/winutils]() was not compatible with my Windows 11 environment, so I rebuilt winutils for Windows 11 x64.

The build procedure is based on the following. Thanks.
https://pivotalbi.com/build-your-own-winutils-for-spark/

## 2. Build Windows11 Spark environment.
### 2.1.Java

Install Java8 and set the JAVA_HOME environment variable.

```
set JAVA_HOME=C:\Java8\jre
``` 

Also set the path to Java.

```
set PATH=%PATH%;%JAVA_HOME%\bin
```

### 2.2.Visual C++ redistribution package.

If you do not have the Visual Studio redistribution package installed, you can download it from

https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2015-2017-2019-and-2022

### 2.3.Hadoop

#### 2.3.1. Download

Download the Hadoop binary from the following
https://hadoop.apache.org/releases.html

#### 2.3.2. Set up SPARK_HOME

Set the environment variable HADOOP_HOME to the location of the unzipped file.

```
set HADOOP_HOME=C:\Users\foo\bar\hadoop-3.3.1
``` 

#### 2.3.3.Path settings

Add HADOOP_HOME\bin to the environment variable PATH.

```
set PATH=%PATH%;HADOOP_HOME\bin
```

#### 2.3.4. Set SPARK_DIST_CLASSPATH

Set the value of the classpath output by hadoop classpath to the environment variable SPARK_DIST_CLASSPATH.

```
>hadoop.cmd classpath
```

## 2.4.winutils
Download this repository and copy the contents of bin in this repository to %HADOOP_HOME%\bin.

## 2.5.Spark
### 2.5.1. Download Apache Spark

Download the Pre-build with user provided hadoop from the Spark download site. (We have tested this for Spark 3.1.2)

https://spark.apache.org/downloads.html

### 2.5.2.Setting up SPARK_HOME

Set the environment variable SPARK_HOME to the location of the unzipped file.

```
set HADOOP_HOME=C:\Users\foo\bar\spark-3.1.2-bin-without-hadoop
```

#### 2.5.3.Path
Add SPARK_HOME\bin to the environment variable PATH.

```
set PATH=%PATH%;SPARK_HOME\bin
```

Once you have done the above, you can start spark-shell !!

-----------------------------------------------------

# winutils
Hadoop版用Windowsバイナリ

## 1. このリポジトリについて
Windows上でSparkを動作させるにはwinutilsが必要となります。このリポジトリのwinutilsは、ASFの公式リリースを作成するために使用されたのと同じgitコミットから直接ビルドされたものです。

現在、[cdarlint/winutils]()のwinutilsバイナリは、私のWindows 11環境と互換性がありませんでしたので、Windows11 x64用にwinutilsをリビルドしました。

ビルド手順は以下を参考にしています。ありがとう。
https://pivotalbi.com/build-your-own-winutils-for-spark/

## 2.Windows11 Spark環境の構築
### 2.1.Javaの準備

Java8をインストールし、環境変数 JAVA_HOMEを設定してください。

```
set JAVA_HOME=C:\Java8\jre
```

またJavaへのパスを設定してください。

```
set PATH=%PATH%;%JAVA_HOME%\bin
```

###  2.2.Visual C++再配布パッケージのインストール

もし、Visual Studio 再配布パッケージがインストールされていない場合は、以下からダウンロードしてください。

https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170#visual-studio-2015-2017-2019-and-2022

###　2.3.Hadoop

#### 2.3.1. ダウンロード

以下よりHadoopのバイナリをダウンロードします。
https://hadoop.apache.org/releases.html

#### 2.3.2.SPARK_HOMEの設定

環境変数HADOOP_HOMEに解凍したファイルの場所を設定してください。

```
set HADOOP_HOME=C:\Users\foo\bar\hadoop-3.3.1
```

#### 2.3.3.Pathの設定
HADOOP_HOME\binを環境変数Pathに追加してください。

```
set PATH=%PATH%;HADOOP_HOME\bin
```

#### 2.3.4.SPARK_DIST_CLASSPATHの設定

hadoop classpathの出力したクラスパスの値を環境変数 SPARK_DIST_CLASSPATHに設定します。

```
>hadoop.cmd classpath
```

## 2.4.winutilsの設定
このリポジトリをダウンロードし、このリポジトリのbinの内容を%HADOOP_HOME%\binにコピーします。

## 2.5.Spark

### 2.5.1.ダウンロード

Sparkのダウンロードサイトから、Pre-build with user provided hadoopをダウンロードします。(Spark 3.1.2ではテストしています)

https://spark.apache.org/downloads.html

### 2.5.2.SPARK_HOMEの設定

環境変数SPARK_HOMEに解凍したファイルの場所を設定してください。

```
set HADOOP_HOME=C:\Users\foo\bar\spark-3.1.2-bin-without-hadoop
```

#### 2.5.3.Pathの設定
SPARK_HOME\binを環境変数Pathに追加してください。

```
set PATH=%PATH%;SPARK_HOME\bin
```

以上までできたら、spark-shellを起動しましょう!
