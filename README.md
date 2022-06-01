# yolov3を用いた物体検出

### セットアップ

0. gitクローンを行う（ローカルに落とす）
```bash
git clone https://github.com/nekobean/pytorch_yolov3.git
cd pytorch_yolov3
```

1. インストールする（依存ライブラリ）
```bash
pip install -r requirements.txt
```

```bash
pip install -U torch torchvision torchaudio
```

2. weightsの中身をダウンロードする
```bash
./weights/download_weights.sh
```

これができない時は、手動で[yolov3.weights](https://pystyle.info/pytorch-yolov3-how-to-use-pretrained-model/#:~:text=bash%20%E3%81%8C%E4%BD%BF%E3%81%88%E3%81%AA%E3%81%84%E3%81%AE%E3%81%A7%E3%80%81%E6%89%8B%E5%8B%95%E3%81%A7%20yolov3.weights%20%E5%8F%8A%E3%81%B3%20yolov3%2Dtiny.weights%20%E3%82%92%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89%E3%81%97%E3%81%A6%E3%80%81weights/%20%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E3%81%AB%E7%BD%AE%E3%81%84%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84%E3%80%82) 及び [yolov3-tiny.weights](https://pystyle.info/pytorch-yolov3-how-to-use-pretrained-model/#:~:text=bash%20%E3%81%8C%E4%BD%BF%E3%81%88%E3%81%AA%E3%81%84%E3%81%AE%E3%81%A7%E3%80%81%E6%89%8B%E5%8B%95%E3%81%A7%20yolov3.weights%20%E5%8F%8A%E3%81%B3%20yolov3%2Dtiny.weights%20%E3%82%92%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89%E3%81%97%E3%81%A6%E3%80%81weights/%20%E3%83%87%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E3%81%AB%E7%BD%AE%E3%81%84%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84%E3%80%82) をダウンロードして、weightsの中へ。

最終的に以下のようになる。
```
weights/
|-- download_weights.sh
|-- yolov3-tiny.weights
|-- yolov3.weights
```

### 実行
```bash
python detect_image.py --input input/cup.jpeg --output output --weights weights/yolov3.weights --config config/yolov3_coco.yaml
```

あとはoutputの中を見れば完了！
