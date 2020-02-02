# おめシスARのようなもの（仮）

おめシスARのようなものを（一部の？）Androidでも楽しめます。

https://mashirowrist.github.io/OmesisAR/model-viewer/

[ARCore supported devices](https://developers.google.com/ar/discover/supported-devices)に記載のあるデバイスで上記のURLを開けばARを撮影する画面に遷移できると思います。

実際に確認した端末は次の通りです。

- Sony Xperia XZ3 (Android 9)

## 3Dモデル

Androidで読み込むために[公式の3Dモデル（*.usdz）](https://github.com/omegasisters/OmesisAR/tree/master/Models)をglTFに変換しています。

1. Xcodeで*.usdzファイルを開く
2. FileメニューのExportでDigital Asset Exchange (DAE)を選択して*.daeとして書き出し
3. [COLLADA2GLTF](https://github.com/KhronosGroup/COLLADA2GLTF)で*.daeを*.gltfに変換

    ```sh
    COLLADA2GLTF-bin unchan_pink.dae unchan_pink.gltf
    ```

実際に変換に使ったバージョンは次の通りです。

- Xcode Version 11.3.1
- COLLADA2GLTF v2.1.5

## 3Dモデルの表示

3Dモデルの表示には[&lt;model-viewer&gt;](https://github.com/GoogleWebComponents/model-viewer/tree/master/packages/model-viewer)を使っています。

## 既知の問題

### 3Dモデル

- ノーマルうんちゃん
    - 色が変わってしまった気がします
    - うんちゃんの目と口の影がうんちゃん本体にかかります
    - ARとして召喚すると途方もなく大きいので、召喚してから小さくしてください
- メタルうんちゃん
    - 正しく変換できていません（実質的に使えません）
    - ARとして召喚すると途方もなく大きいので、召喚してから小さくしてください
- 銀盾
    - ARとして召喚すると途方もなく大きいので、召喚してから小さくしてください
