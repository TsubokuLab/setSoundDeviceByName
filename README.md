# setSoundDeviceByName
ショートカットで規定のサウンドデバイスを変更するやつ。

ほとんど以下のサイトで紹介されているスクリプトがベースですが、使いやすくする為にサウンドデバイス名を入力する方式に調整しています。

↓偉大な先人の知恵🙏

> Windowsの音声出力先を変えるショートカット作成 - itiblog  
> https://itib.hatenablog.com/entry/2021121001



## 使い方

1. Download ZIPするなりして、以下の2つのファイルを適当な場所に保存

   * setSoundDeviceByName.ps1

   * ヘッドフォン切替ショートカットのサンプル.lnk

2. タスクバーのサウンドアイコンを右クリックしてサウンドウィンドウを開く
   ![スクリーンショット 2024-08-13 163509](https://github.com/user-attachments/assets/a0d7b0c6-6404-48b4-a239-1861c6c89e84)

3. サウンドの再生デバイス一覧から切り替えたいサウンドデバイスの名前をメモしておく
   ![image](https://github.com/user-attachments/assets/7645c040-65fc-4dc6-89de-2781a07ed709)

4. ヘッドフォン切り替えショートカットサンプルを右クリックしてプロパティを開く
   ![image-20240813164446998](C:\Users\tsubokura\AppData\Roaming\Typora\typora-user-images\image-20240813164446998.png)

5. プロパティのリンク先を以下のルールにそって変更

   ```
   C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -ExecutionPolicy RemoteSigned -File [setSoundDeviceByName.ps1までのファイルパス] "[変更したいサウンドデバイス名]"
   ```

   例えば、.ps1スクリプトが`D:\Downloads\setSoundDeviceByName\setSoundDeviceByName.ps1`に保存されていて、`ヘッドセット イヤフォン`というサウンドデバイスに変更したい場合は、

   ```
   C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -ExecutionPolicy RemoteSigned -File D:\Downloads\setSoundDeviceByName\setSoundDeviceByName.ps1 "ヘッドセット イヤフォン"
   ```

   のようになります。

   ※ショートカットキー欄は、不要であれば空欄に設定して下さい。  
   ※ショートカット名やアイコンも適当なものに変更して下さい。  
   ※セキュリティの関係？でショートカットからの起動に失敗する為、先人ブログのものから起動オプションに`-ExecutionPolicy RemoteSigned`を追加しています。  

6. ショートカットをタスクバーにドラッグアンドドロップするなりして登録

   ![image](https://github.com/user-attachments/assets/78bc5e62-d2c3-4f3b-a905-f31fe17d4e38)
   ※サウンドデバイス名を変更した後はタスクバーに登録し直さないと何故か反映されないので注意  

7. ショートカットを実行して動作を確認

8. 完了！
