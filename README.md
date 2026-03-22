# FilmGrade - 本番デプロイ手順書

FilmGradeを世界中に公開し、実際のユーザーが使えるようにするための手順です。

## 1. Vercel での公開 (最も簡単)
1. [Vercel](https://vercel.com/) にログイン。
2. 「Add New...」 -> 「Project」を選択。
3. このフォルダ（`color AI`）をアップロードするか、GitHub経由でインポート。
4. 公開されたURL（例: `film-grade-xxx.vercel.app`）をコピー。

## 2. Firebase を本番URLに対応させる
1. [Firebase Console](https://console.firebase.google.com/) にアクセス。
2. 構築したプロジェクトを選択 -> 「Authentication」 -> 「Settings」 -> 「Authorized domains（承認済みドメイン）」。
3. 「Add domain」をクリックし、先ほどの Vercel のURL（例: `film-grade-xxx.vercel.app`）を追加。
   - これで、そのURLでもGoogleログインが許可されるようになります。

## 3. Stripe を本番モードにする
1. [Stripe Dashboard](https://dashboard.stripe.com/) で「テストモード」をオフにします。
2. 「支払いリンク（Payment Links）」を作成し、FilmGrade PROプランなどの商品を作ります。
3. `index.html` 内の `plan-pro` のクリックイベントを、作成した本番用URLへ遷移するように書き換えます。

---
🎉 これで、世界中のクリエイターがあなたのアプリを使って、課金できるようになります！
