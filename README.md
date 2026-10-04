# KPIダッシュ!街まわり営業

飲食店への外回り営業を5日間シミュレーションする3Dゲーム。訪問・商談・受注・売上のKPI達成を目指す。

- 公開URL: https://wa-ra-so.github.io/kpi/
- GitHub Pages は「Deploy from a branch: main / (root)」で公開。`main` に入ると数分で反映される
- スマホではブラウザの「ホーム画面に追加」でアプリとして使える(PWA)

## ファイル構成

| ファイル | 役割 |
|---|---|
| `index.html` | ゲーム本体(単一ファイル) |
| `three.min.js` | three.js r128(MIT)。読めないときは cdnjs から読み込む |
| `sw.js` | Service Worker。github.io 上でのみ登録し、本体をキャッシュしてオフラインでも起動できるようにする |
| `manifest.webmanifest` / `icon-*.png` / `apple-touch-icon.png` | ホーム画面追加用 |

## ローカルで開く

```sh
python3 -m http.server 8000
# → http://localhost:8000/
```

`index.html` を直接開いても動く(Service Worker は登録されない)。フォントは Google Fonts から読み込むため、オフラインだと代替フォントになる。

## 更新時の注意

`index.html` 以外のファイル(`three.min.js` など)を差し替えたときは、`sw.js` の `CACHE` の値(`kpidash-v1`)を上げる。上げないと、インストール済みの端末に古いファイルが残る。

※ 街・店名・人物・価格はすべて架空です。
