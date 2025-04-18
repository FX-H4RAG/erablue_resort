;_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
;パッチ名：フィルタソート機能改修
;作者：
;更新日：2025/2/8
;
;作成内容の概要：
;◆2025/2/8更新分
;　○フィルタボタンの横に「現在適用中のフィルタ項目」の表示を追加
;　　・今フィルタ中なのかパッと見でわからない場合があったので表示を追加。
;　　・詳細に表示しようとすると表示が長くなりすぎる可能性があるので、項目単位での表示にしています。
;
;　○フィルタ画面に「全項目全て表示」ボタンを追加
;
;　○ニューゲーム時の初期従業員選択のフィルタソート処理に汎用処理を使用するように変更
;
;　○出典フィルタに全作品強制表示モードを追加
;　　・初期従業員選択処理用。EXキャラが全員招待不可状態でグラブル以外の作品が表示されなかったため。
;
;　○出典フィルタの表示作品数を調整
;　　・1列3個表示で最終行だけ1個表示になっていたため調整。
;
;　○弱点フィルタと出典フィルタに「全て表示」ボタンを追加
;　　・フィルタ設定画面を開かなくても設定リセットができるようにしました。
;
;　○フィルタソート機能を使用しているキャラ選択画面にソート情報表示を追加
;　　・対象は「スイートルーム招待」「縁結び」「招待制御例外規定設定」
;
;　○不具合修正
;　　・出典フィルタ、弱点フィルタのボタンを押した際にフィルタ設定用配列に不要な文字列が追加されていたのを修正
;
;　○その他
;　　・フィルタ機能、ソート機能のリファクタリング
;　　・フィルタ設定なし項目のフィルタ判定をスキップして高速化
;　　・誤記修正：出展作品→出典作品
;　　・使用しなくなった変数を削除
;
;
;◆2025/2/2更新分
;　○フィルタ項目に画像フィルタ「画像あり」「画像あり(水着)」「画像あり(裸)」「画像なし」を追加
;
;　○ソート項目に「呼び名ソート」「感覚合計」を追加
;
;　○フィルタ機能の処理速度向上
;　　・無限ループ対策を「10%ごとにAWAIT」から「1秒ごとにAWAIT」に変更。
;
;　○フィルタ機能、ソート機能のリファクタリング
;　　・設定部分と実行部分が別ファイルになっていたので機能ごとにまとめ。
;　　・よく使われる処理を関数化。
;
;　○EXキャラ招待リストのフィルタ/ソート機能改修
;　　・EXキャラ招待リスト用のフィルタ/ソート設定は別枠に保存するようになっています
;　　・フィルタ/ソート処理の処理速度向上
;　　・ページ移動ボタンに一気に移動するボタンを追加
;
;　○素質変化メニューのフィルタ/ソート機能改修
;　　・キャラ名の横にソート情報の表示を追加
;　　・ページ移動ボタンに一気に移動するボタンを追加
;
;　○不具合修正
;　　・画像数に画像以外のファイル(テキスト等)もカウントしていたのを修正
;
;_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/_/#
;ライセンスについて
;	・基本項目(許可する項目を"○"に、許可しない項目を"×"に変更してください。)
;	+----+----+-------------------------------------------+
;	|番号|許可|ライセンス内容                             |
;	+----+----+-------------------------------------------+
;	|   1| ○ | 処理上のバグ修正                          |
;	+----+----+-------------------------------------------+
;	|   2| ○ | 新規機能追加による内容改変                |
;	+----+----+-------------------------------------------+
;	|   3| ○ | バランス調整による内容改変                |
;	+----+----+-------------------------------------------+
;	|   4| ○ | 口上の誤字・脱字の修正                    |
;	+----+----+-------------------------------------------+
;	|   5| ○ | 口上の新規追加・加筆                      |
;	+----+----+-------------------------------------------+
;	|   6| ○ | 既存口上の改変                            |
;	+----+----+-------------------------------------------+
;	|   7| ○ | 改変した口上の自由な再配布                |
;	+----+----+-------------------------------------------+
;	|   8| ○ | 口上内容の転載（erablue_resort内部に限る）|
;	+----+----+-------------------------------------------+
;	|   9| ○ | erablue_resort本体への収録                |
;	+----+----+-------------------------------------------+
;※１～８番の項目のいずれかを許可していない場合、９番の項目は自動的に許可していないと扱います
