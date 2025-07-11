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

## 2025-07-04
- secretを書いて適応したのでmariadbの起動は確認
- serviceを作成したが見本が間違えている可能性
  - https://kubernetes.io/ja/docs/concepts/workloads/controllers/statefulset/
- serviceをどうにかする

## 2025-07-07
- servicesをなんとか作成に成功
- 次はtraqのdeployかな？

## 2025-07-08
- backendのstatefulsetは作れた
- configmapは作成できたが、どことなにが適応するかわかってない
- `.name: Not found: "traq-backend-config"` をこれを解決する

## 2025-07-09
- backendのconfogmapをマウントすることに成功
- mariadb内のuser作成環境変数があり、そこでtraqのuserを作成
- 基本的にsecretはbase64にしなければならないのを忘れていて文字化け、対処する

## 2025-07-10
- base64は対処した
- 環境変数も問題ない
- なぜかユーザーが作られず、ChatGPTが調子わるくて終了、またみる

## 2025-07-11
- pvcを削除しないとキャッシュが残る仕様らしく、mariadbを消した
- 根本原因は`echo -n`を付けないと\nが入ることを認知できていなかったsecret
-`ghcr.io/traptitech/traq:latest`がpullできなくなって一旦お預け
