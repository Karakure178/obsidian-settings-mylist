---
created: <% tp.file.creation_date() %>
tags: ["DailyNote"]
---
tags:: [[+Daily Notes]]

# <% moment(tp.file.title,'YYYY-MM-DD').format("YYYY MMMM DD, dddd") %>

<< [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').subtract(1, 'd').format('YYYY-MM-DD-dddd') %>|前の日]]| [[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD-dddd').add(1, 'd').format('YYYY-MM-DD-dddd') %>|次の日]] >>

---
## 📅 本日のタスク
##### 🚀 重要度5
- [ ]  

##### 🍃 重要度1
- [ ] 

##### 👎 本日の振り返り
- 
<% tp.file.cursor() %>

---
## 本日のおすすめ記事
<% tp.file.include("[[randomDevNotes]]") %>

---
## 今日作った記事
```dataview
TABLE tags
FROM "" 
WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
WHERE contains(aliases, "開発ログ")
```

## 今日更新した記事
```dataview
List 
FROM "" 
WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```