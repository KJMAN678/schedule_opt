## コード元
- 久保幹雄先生の Python言語による実務で使える100+の最適化問題 [乗務員スケジューリング問題](https://mikiokubo.github.io/opt100/80csp.html#%E4%B9%97%E5%8B%99%E5%93%A1%E3%82%B9%E3%82%B1%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AA%E3%83%B3%E3%82%B0%E5%95%8F%E9%A1%8C)  

## 使用データセット
[こちら](http://people.brunel.ac.uk/~mastjjb/jeb/orlib/ptaskinfo.html) にある csp50.txt

## 変更点
- pandasのDataFrame型を読み込んで最適化するように変更
- networkx のノード表示する際に何番目のデータに相当するノートなのかわかるように、テキストを合わせて表示するようにした
![ダウンロード](https://user-images.githubusercontent.com/45703844/132967322-82e9f391-38a6-413e-bc09-93f1f0cc9e31.png)
- 最適化結果（スケジュールの組み合わせ）を pandas の DataFrame で出力した
  - group の数字が同じものが組み合わされたスケジュール
<img width="201" alt="2021-09-12_10h06_34" src="https://user-images.githubusercontent.com/45703844/132967354-ad6649f6-9ef3-40e9-81b4-e3a2cd3df49b.png">
- 組み合わせ可能なスケジュール候補 cost_df(time_df の start ～ finish 処理時間帯 が重複しない組み合わせ) をロジックで作成するようにした  
- 計算量軽減のため、time_df 50個からサンプルで30個に絞っている

## その他
- [Google Colab](https://colab.research.google.com/drive/1q417zxbnmMfRkzrWquQo-27ehJ0bCYo2?usp=sharing)
- gurobi - Error code = 10004 Unable to retrieve attribute 'X' は最適化に失敗すると出るエラー  
[参考サイト](https://stackoverflow.com/questions/19270102/gurobi-error-code-10004-unable-to-retrieve-attribute-x)
