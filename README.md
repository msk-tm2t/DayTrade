# DayTrade

- 2025年は実弾でがんばろう！
- 株メイドゆーかりさんが儲かる記録をつけるために2025年版を作ったよ
- 松井証券でデイトレやってる人だったら誰でも使えます
- 今回はＳＢＩ証券版も作りました


注意事項
- 個人投資家が利用することを想定しています
- 無料配布していますが著作権は放棄していません
- 不備等があった場合に発生したいかなる損害に対しても保証は行いません
- 自社・自身の製品のヒントとすることは問題ありませんが、そのまま販売したり何らかの付属品としての配布は禁止します


推奨銘柄場中監視について
- 基本的に無料で公開するのは変わりません
- 2024年7月末にトレーダーTOMOさんのサロンに入会
- 入会理由はレーザーテックに固執する当時のトレードは退場を余儀なくされると考えていたためです
- TOMOさんの教えの一つ「バスケット投資」という「複数銘柄でトータルプラスを目指す」という考えに影響されました
- 私は学生時代から社会人の時も一貫してシングルタスクな人間で複数銘柄を監視することができない性分でした
- そのためデイトレ配信を始めた2022年11月からレーザーテックに絞り、トレンド解析のために作ってきた分析ツール（Excel）
- バスケット投資に対応する形でレーザーテックだけでなく50銘柄を監視できるツールに変更しました
- 改変前はレーザーテックだけを直近の四本値・出来高の時系列データに対して複数インジケータの変化を通してトレンドが上昇か下落かを判定するもの
- これを50銘柄の一覧表示、四本値の時系列をすて、板読みのための情報を取得する仕様に変更しています
- サロン入会前にはなかった板のUNDER/OVERを投資判断に使ったり、サロンの推奨銘柄の撤退ラインを入力できるようになったりと機能改善
- 色々機能盛りだくさんにしたら。。。。データ更新が頻繁過ぎて処理が遅延して動かなくなった
- で、困っていたらおんなじことかんがえる人がTOMOさんのサロンにいた
- それが「株ナビシート」というものでスゴイ見た目も素敵で比べ物にならないぐらいすごいツール
- 直近の歩み値をどう判断するかとか同じような苦労をしてて協力したいなって思ったものの。。。
- 当初は無料というか有志で利用・改善していたようですが途中から3万円ぐらいで販売されることになり基本的な考え方違うなと思い距離を置くことにしました
- 相手は販売しているので私の監視ツールを先方が見つけた時に「マネされた」とか「アイデア盗まれた」とか言われないように自己防衛のためツールを公開し機能の改善やいつ使っていたのかを記録しておくことにします
- なお、見せ方とかすごく参考になるのでそういうところはマネしてます
- でも手動でデータコピーとか嫌いなので、VBAマクロとPythonで自動更新するのが基本コンセプト
- 出来高取得の方法とか教えてあげようかなとも思ったのですが、こちらのツール渡すことになって変ないざこざが怖かったので止めてみたり
- いろいろとチューンナップして何とか動くところまでこぎつけたのでデイトレ配信でも画面表示させることを検討しています
- 最後にこのツールのコンセプトを以下に列挙
- 場中は基本的に一覧の情報からエントリがNGになったら警告し、銘柄・タイミングのエントリ判断をするツールです
- 「株ナビシート」はどちらかというとエントリーする理由を探すツールなので根本的に発想が真逆だと私自身は認識してます
- 判断で重要だと認識しているのは以下の通り
- ①1日の出来高が大事、想定される1日の出来高が30万株以下の出来高推移をたどっていればエントリさせない
- ②出来高の推移が大事：分単位で当日の出来高と5日間平均を比較し出来高の進捗が30%以上悪化していればエントリさせない
- ③板読みが大事：売買3ティックの板読み、板は厚い方に動くので買板が厚い時はエントリさせない（売１：買３を基準に）
- ④板読みが大事：売買残り7ティックの板読み、板は厚い方に動くので買板にでっかい気配値があればエントリさせない（売１：買１０を基準に）
- ⑤大口に逆らわない：直近歩み値30約定を判断基準に大口の売が出た場合はエントリさせない（投資額1千万を基準に）
- ⑥出来高が大事：直近歩み値30約定の出来高売買率を算出し売約定が多い時はエントリさせない（売３：買１を基準に）
- ⑦板の気配が大事：UNDER/OVERの数量比率を算出し売優勢だとエントリさせない（売５：買１を基準に）　※③と④とは逆の考え
- ⑧板の気配が大事：いた全体の数量比率を算出し売優勢だとエントリさせない（売１０：買１を基準に）
- ⑨ライントレードが大事：撤ラインを割った銘柄にはエントリさせない（サロンや予習で引いたラインを事前入力→さすがにこの自動化が出来てれば自動売買作るって）
- 株なびシートとの違い
- 出来高は同時刻５日平均との比較し、推定出来高を事前に把握するのが異なる
- 板読みの解像度が細かく、気配値の3ティック、残り7ティックで基準を変えて強度を測る（厚い方に動く考え方が特徴）
- トレード手法が亜流スキャルピングなのでサロンのエントリタイミングとは本質的に違っているので判断する材料も異なっている
- 未実装だが、寄り値からの値幅について過去の推移から上限下限を算出して判断材料できるように改善したい
- これについては当日TRとATRの比較とかやってみたものの収集つかなくなって判断材料にならなかったので実績ベースで判断する方針に変更
