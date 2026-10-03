# Voice-changer 即時變聲器

單一檔案的網頁變聲器：把外接麥克風的聲音即時變聲，再透過「虛擬音源線」送進 LINE / Discord 電腦版通話。所有處理都在瀏覽器本機完成，不會上傳聲音。

```
🎤 外接麥克風 → 🎛️ index.html(變聲) → 🔌 虛擬音源線 → 💬 LINE / Discord
```

## 使用方式

1. 安裝免費的虛擬音源線
   - Windows：[VB-CABLE](https://vb-audio.com/Cable/)（以系統管理員身分執行 `VBCABLE_Setup_x64.exe`，裝完重新開機）
   - macOS：[BlackHole 2ch](https://existential.audio/blackhole/)（或 `brew install blackhole-2ch`）
2. 用 Chrome 或 Edge 打開 `index.html`（可直接雙擊開檔，或放到 GitHub Pages），按「啟動變聲」並允許麥克風。
3. 網頁裡：**輸入** 選外接麥克風，**輸出到通話** 選 `CABLE Input`（Mac：`BlackHole 2ch`）。偵測到時會自動選好。
4. 通話軟體的麥克風選 `CABLE Output`（Mac：`BlackHole 2ch`）
   - Discord：使用者設定 → 語音與視訊 → 輸入裝置
   - LINE 電腦版：設定 → 通話 → 麥克風
5. 想聽自己的聲音：**監聽** 選耳機。

## 功能

- 10 種預設：原聲、高音/女聲、低沉/男聲、花栗鼠、怪獸、機器人、外星人、電話/對講機、山洞回音、演唱會
- 細部調整：音高（±12 半音）、環形調變、失真、高低頻截止、回音、殘響、音量
- 輸入／輸出音量表、靜音按鈕、輸出限幅器（防爆音）
- 變調使用 AudioWorklet 延遲線顆粒法，搭配互相關波形對齊，延遲約 30 ms

## 限制

- 只能用在電腦版通話；手機系統不允許其他 App 當麥克風。
- 需要能選擇輸出裝置的瀏覽器（Chrome / Edge 110+）。Safari 不支援。
- Discord 建議關閉「雜訊抑制（Krisp）」和「回音消除」，否則效果可能被濾掉。
