# FQsolverData
能用在 FQsolvers 的資料集。請至 https://github.com/light-chen-light/FQsolvers 下載主程式。

## 檔名：
檔名分為三段。
* 上傳日期
* 活動名稱
* 對應的 FQsolver 版本

例如 20210127kamakuraM1 是在2021年1月27日上傳，針對鎌倉活動和M1版本的FQsolver所做

## 使用方法/檔案內容
* 將需要的檔案下載至MATLAB資料夾
* 用 MATLAB 指令 "load" 讀取資料
* * MissionName 是 m×1 cell 矩陣，為各個活動需求的名稱
* * Mission 是 m×1 double 矩陣，代表活動的需求
* * FQName 是 n×1 cell 矩陣，為各個自由任務的名稱
* * AP 是 n×1 cell 矩陣，代表各個自由任務的AP消耗
* * Contr 是 m×n double 矩陣，代表各個自由任務對各項活動需求的貢獻
* 定義變數 Reach，代表已達成的部分。建議使用下列其中一項指令然後再調整。
* * Reach=zeros(size(Mission));
* * Reach=Mission;
* 執行 FQsolver

## 小技巧
* 可以依照喜好微調AP，喜歡的關卡調低，不喜歡的關卡調高，完全不想打的關卡調到非常高
* 如果不想以AP為判斷基準的話也可以自行決定數值(數值越低表示越能接受，但需為正數)
* 輸入並執行此指令可以顯示各任務狀況
* * cat(2,MissionName,mat2cell(Mission,ones(1,length(Mission))),mat2cell(Reach,ones(1,length(Reach))))
* 輸入並執行此指令可以顯示各關卡的AP
* * cat(2,FQName,mat2cell(AP,ones(1,length(Mission))))
