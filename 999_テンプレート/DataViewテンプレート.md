## Dataviewクエリ例

**対戦記録を一覧表示**

````markdown
```dataview
TABLE 日付, 相手キャラ, 結果, LP変動, LP
FROM #対戦記録
SORT date DESC
```
````

**勝敗をカウント**

````markdown
```dataview
TABLE 結果, length(rows) AS 回数
FROM #対戦記録
GROUP BY 結果
```
````

**特定キャラとの対戦だけ絞り込む**

````markdown
```dataview
TABLE date, 結果, LP変動
FROM #対戦記録
WHERE 相手キャラ = "ルーク"
SORT date DESC
```
````