## 2025-06-30
- kubernetes環境作った
- ヒントのみで作ってみる
- 次はMariaDBをdeployする


## 2025-07-01
- mariadbのマニフェストかいた
- 動くかわからない
- StatefulSetの項目みたらapply


## 2025-07-03
- pvcのstrageclassが作成されているものを対象につくらないとだめ
- namespaceがないので作成、StatefulSetとpvcは削除しないと一部変更できない
- 明日はmariadbが起動しない問題を解決する
