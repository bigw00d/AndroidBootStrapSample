Android_SensorMonitor（EnOceanセンサーデータ表示アプリ）
====

EnOceanの無線データ受信アプリケーションです。

## Description
* 標準版のアプリケーションです  
* カスタム仕様のアプリケーションはブランチで管理します  

## Requirement

* Android Studioはバージョン3.3.2を使用しています  
　※他のプラグイン等はAndroidStudioのダイアログに従ってアップデートしてください

## Usage
### センサーの登録
1. アプリケーションを立ち上げてセンサーから登録用データを受信します
1. 画面右下の赤いボタンを押下すると未登録センサーの一覧にセンサーが表示されます
1. そのセンサーを選択して未登録センサーの一覧画面を消すと登録は完了です  
　※右上の三点リーダーを押した後に「Hide Sensor List」を選択すると、左の登録済みセンサー一覧を消すことができます

## Install
1. gas_sensor_appプロジェクトで生成したapkファイルをAndroid端末に転送します
1. Android端末にてファイルマネージャ(例：Files by Google）を使用してapkファイルを選択してインストールします

### ライブラリの更新手順
1. sensor-libプロジェクトをビルドします
1. ビルドして生成される「gas-sensor-lib-debug.aar」を「sensor-lib-1.0.36.aar」にリネームします
1. リネームしたファイルをgas_sensor_app\app\libsに置きます  
1. gas_sensor_appプロジェクトをビルドし直してapkファイルを生成します  
※ライブラリのバージョンを変える場合はloonai_watcherプロジェクトのビルド前にloonai_watcher\app\build.gradleの以下"version"を変更します
```
compile(group: 'com.nissha', name: 'sensor-lib', version: '1.0.36', ext: 'aar')
```

### gas_sensor_appプロジェクトのインポート&apkファイルの生成(Android Studio3.3.2を使用する場合)
1. gas_sensor_appプロジェクトをAndroidStudioでインポートします
1. Gradle Syncのウィンドウ(「... Click 'OK' to use the Gradle wrapper, ...」)は「OK」を選択します
1. Add Files to Gitのウィンドウは「Remember, don't ask again」にチェックを入れて「No」を選択します
1. Android Gradle Plugin Update Recommendedのウィンドウは「Don't remind me again for this project」を選択します  
1. Gnerate Singed Bundle or APK -> APKにチェックでNext -> key storeを選択してNext -> Build Variantsは「release」で「V1(Jar Signature)」にチェックを入れてFinishを押す    
1. gas_sensor_app/app/releaseフォルダにapkファイルが生成されている  

## Document

* [ソフトウェア仕様書](./doc/01_ソフトウェア仕様書)
* [ソフトウェア設計書](./doc/02_ソフトウェア設計書)
* [ソフトウェア検査結果](./doc/03_ソフトウェア検査結果)

## Ticket

 [#1534 車両衝突通知システム：標準版のアプリを用意する](http://163.49.60.156:8280/redmine/issues/1534)

## Licence

   Copyright (C) 2018-2019 Nissha Co., Ltd. All rights reserved.

## Author

* r23_v1.0.0 [Daiki Yasuda](mailto:daiki.yasuda@yasuda-tech-studio.info)
