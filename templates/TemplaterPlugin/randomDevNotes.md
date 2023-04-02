<%* 

const randomDevNotes = []
app.metadataCache.getCachedFiles().forEach(filename => {
	if(app.metadataCache.getCache(filename).frontmatter !== undefined){
		//tR +=`${filename} `
		let alia = app.metadataCache.getCache(filename).frontmatter.aliases
		if(Array.isArray(alia) && alia.includes("開発ログ")){
				//tR += `${alia}
//`
randomDevNotes.push(filename)
		}
	}
})

var i = 0
    do {
        const randomIndex = Math.floor(Math.random() * randomDevNotes.length)
        //同じ数字ダブって入っていると思われる
        tR += `- [[${randomDevNotes[randomIndex]}]]` + "\r\n"
        i++
    } while (i<3)
%>