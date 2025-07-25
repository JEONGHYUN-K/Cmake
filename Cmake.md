# CMakeメモ
## 1. CMakeとは？
CMakeは、クロスプラットフォーム対応のビルド自動化ツールです。

C/C++などのソースコードを各OS・コンパイラ向けにビルド設定（MakefileやVisual Studioプロジェクトなど）を自動生成します。

つまり、「ビルドシステム生成ツール」です。

## 2. なぜ使うのか？
プラットフォーム（Windows、Linux、macOS）ごとに異なるビルド設定を書く手間を減らすため。

複雑なプロジェクトで依存関係やビルド手順を管理しやすくするため。

## 3. 基本のファイル構成
CMakeLists.txt（ビルド設定ファイル）
cmake
コピーする
編集する
cmake_minimum_required(VERSION 3.10)  # CMakeの最低バージョン指定
project(MyApp)                        # プロジェクト名

add_executable(MyApp main.cpp)       # 実行ファイル名とソースファイルを指定
## 4. 使い方（簡単な流れ）
プロジェクトのルートに CMakeLists.txt を作成する。



ターミナル（コマンドプロンプト）でビルド用フォルダを作る：

bash
コピーする
編集する
mkdir build
cd build


CMakeを実行してビルドシステムを生成：

bash
コピーする
編集する
cmake ..


ビルドを行う（Makefileの場合）：



bash
コピーする
編集する
make


実行ファイルが生成されるので実行：

bash
コピーする
編集する
./MyApp
## 5. 補足
WindowsでVisual Studioを使う場合、cmake .. を実行すると .sln ファイルが生成され、IDE上でビルドできる。

複数のソースファイルを指定したい場合：

cmake
コピーする
編集する
add_executable(MyApp main.cpp utils.cpp)


ライブラリを作るときは：

cmake
コピーする
編集する
add_library(mylib utils.cpp)
## 6. まとめ
用語	説明
CMake	:  ビルド設定ファイルを生成するツール

CMakeLists.txt  : 	CMakeの設定を書くファイル
ビルド	ソースコードを実行ファイルに変換する処理

