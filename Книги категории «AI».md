---
cssclasses:
  - wide-85
---
# AI (`$= dv.pages("").where(page => {if (page["Тип"] && page["Тип"].path == "types/Книга.md" && !["templates", "templater"].includes(page.file.folder) && page.Категории.contains("AI")) {return page;}}).length`)

```dataviewjs
// import code
eval(
    (await app.vault.read(app.vault.getAbstractFileByPath("dataviewjs/books.md")))
    .replace("```js", "").replace("```", "")
);

const booksFiles = window.books.getBooks()
    .where(p => p["Категории"].contains("AI"))
    .sort(p => p["Добавлена в базу"], "desc");

dv.el("div", window.books.renderBooks(booksFiles, book => `добавлена ${window.books.formatDate(book["Добавлена в базу"])}<br>`), {cls: "books"});
```