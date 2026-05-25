# データベース設計

ゲーム管理に必要な基本テーブルを以下のように定義します。

## games

ゲーム単位の情報を管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | ゲームID |
| title | text | ゲーム名 |
| description | text | 概要 |
| status | text | 企画中、制作中、公開済みなどの状態 |
| created_at | datetime | 作成日時 |
| updated_at | datetime | 更新日時 |

## assets

画像、音声、フォント、資料などの素材を管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | アセットID |
| game_id | integer | 関連するゲームID |
| name | text | アセット名 |
| type | text | 画像、音声、UI、資料などの種別 |
| path | text | リポジトリ内の保存パス |
| license | text | ライセンス情報 |
| created_at | datetime | 作成日時 |
| updated_at | datetime | 更新日時 |

## tasks

制作作業や確認作業を管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | タスクID |
| game_id | integer | 関連するゲームID |
| title | text | タスク名 |
| description | text | 作業内容 |
| status | text | 未着手、進行中、完了などの状態 |
| priority | text | 優先度 |
| due_date | date | 期限 |
| created_at | datetime | 作成日時 |
| updated_at | datetime | 更新日時 |

## bugs

不具合や修正状況を管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | バグID |
| game_id | integer | 関連するゲームID |
| title | text | バグ名 |
| description | text | 内容 |
| steps_to_reproduce | text | 再現手順 |
| expected_result | text | 期待される結果 |
| actual_result | text | 実際の結果 |
| status | text | 未対応、調査中、修正済みなどの状態 |
| severity | text | 重要度 |
| created_at | datetime | 作成日時 |
| updated_at | datetime | 更新日時 |

## production_logs

制作ログや作業記録を管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | ログID |
| game_id | integer | 関連するゲームID |
| title | text | ログタイトル |
| body | text | 記録内容 |
| logged_at | datetime | 記録日時 |

## references

参考資料や外部リンクを管理します。

| カラム | 型 | 説明 |
| --- | --- | --- |
| id | integer | 参考資料ID |
| game_id | integer | 関連するゲームID |
| title | text | 資料名 |
| url | text | URL |
| note | text | 補足メモ |
| created_at | datetime | 作成日時 |
