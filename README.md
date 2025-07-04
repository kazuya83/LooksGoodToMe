# Looks Good To Me 〜みんなのコードレビュー〜

## コードレビューの目的
- チーム内のルールを満たしてるかを確認する(コーディング規約から外れていないか)
- 仕様を満たしてるか

## コードレビュー・PRのガイドライン
- ~~レビュー時間：45〜60分~~
- レビュー時間：25〜45分
- 合計500行を超えるコードでPR出さない
- PRで変更されるファイルは20ファイル未満

## レビュー準備完了と言えるPR
以下全てに「はい」と回答できてる状態
- タイトルは簡潔か？
- 変更についての明確な説明はあるか？
- 変更に関連するドキュメントは完全で、PRに含まれているか？
- コミットメッセージは、わかりやすく、明確で、アドミックか？
- 関連するテストが、作成および/または更新され、PRに含まれているか？
- チケット番号/スプリントタスクがリンクされているか？
- 事前チェック、テスト実行、その他の自動化された前提条件は実行が完了し、合格しているか？

## DORA指標
コードレビュー効果測定する（メリットを伝える）ための指標

| DORA指標 | 測定方法と<br/>指標の解釈 | 指標が重要な理由 | 組織が関心を<br/>持つべき理由 |
|----|----|----|----|
| **デプロイ頻度**<br/>本番環境にコードをデプロイする頻度 | 1日あたりのデプロイ回数<br/>良好：必要に応じて、高頻度、1日に複数回デプロイ<br/>不良：低頻度、月に１回から半年に１回 | チームの作業プロセスとリリースプロセスの効率性を示す | チームが顧客に価値を提供する頻度を示す |
| **平均変更リードタイム**<br/>コードがコミットされてから、正常に実行されるまでの時間 | コミットされた変更が、本番環境で正常に実行されるまでの平均時間<br/>良好：1日未満<br/>不良：1ヶ月〜半年 | チームのペースを追跡する。早いチームは、プロセスを最適化している。遅いチームは、プロセスに無駄や非効率的な部分がある可能性がある | より迅速な提供は、終映機の増加や顧客更新率の向上につながる |
| **平均復旧時間** | 本番寛容において、バグや障害が報告されてから、その問題が修正されるまでの平均時間<br/>良好：1時間未満<br/>不良：１週間から1ヶ月 | 本番環境で発生する問題を理解し、解決するまでの速さを示す。平均復旧時間が短いと、本番環境が影響を受けた場合でも、正常状態に復旧できるという自信が生まれる | ダウンタイムは組織に悪影響を及ぼす。システムが早く復旧するほど、組織ヘの影響は小さくなる |
| **変更障害立**<br/>本番環境にリリースした変更が障害を引き起こす頻度 | 障害数とデプロイ数の比率<br/>良好：0〜15%<br/>不良：46〜60% | チムが構築するソフトウェアの品質を示す。変更障害率が高いということは、ソフトウェアの品質が低く、顧客を不満にさせていることを示す | バグ修正とコードのロールバックにはコストがかかり、顧客に価値をもたらす新機能の構築に費やす時間が奪われる |

# コードレビュープロセス実践項目
- 方法ではなく、理由をドキュメント化する
- 経験の浅いメンバーを「情報共有レビュー担当者」とする

# コードレビューワークフローの目的
- 新しいチームメンバーが、チームのコードレビュープロセスを理かうできるようにするため
- チームメンバー全員が、ワークフローのステップを明確に参照できるようにするため
- ワークフローを通じて、チームのレビュープロセスを実施する全員が、各フェーズで何が期待され、角フェーズの前後に何が起こるのかを理解できる様にするため
- チームのワークフローに対する認識を一致させるため

# レビューの焦点
- 複雑さ
  コードは理解できるか？わかりやすいか？将来、他の開発者が再びこのコードを見た時に、依然として明確に理解できるか？
- 整合性
  提案された変更は、すでに機能し、信頼性を高く、確立されたプロジェクト内の設計パターンやプラクティスにしたがっているか？
- 規約
  業界全体の規約を守ってるか？コードは、ライブラリ、フレームワーク、プログラミング言語、ソントアの確立された規約にしたがっているか？
- クロスプラットフォーム互換性
  コードベースは、クロスプラットフォーム互換性を考慮する必要があるか？
- ドキュメント
  ドキュメントが不足している場合に承認を止めるか？関連ドキュメントの更新は、PRのチェックリストに含まれるか？
- エラー処理
  エラーと例外の処理に関する明確なガイドラインはあるか？それらは、コードベース全体で一貫して実装されているか？
- 命名
  チームに命名規則がある場合、それに従っているか？
- リソース管理
  （メモリ、ネットワーク接続、入出力操作などの）リソースの管理は、適切に考慮されているか？
- 拡張性
  コードは、大きなリグレッションを起こさずに、リファクタリングや書き直しできるか？
- セキュリティ
  自動化された手段では検出されない明らかなセキュリティの脆弱性はあるか？
- テスト
  テストが不足している場合に、承認を止めるか？

