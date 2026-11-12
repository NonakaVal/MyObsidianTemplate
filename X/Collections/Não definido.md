```dataviewjs
const pages = dv.pages()
    .where(p =>
        p.collection == null &&
        !p.file.path.startsWith("X/")
    )
    .sort(p => p.file.mtime, "desc")
    .limit(10);

function relativeTime(date) {
    if (!date) return "—";

    const diff = Date.now() - date.toMillis();
    const minutes = Math.floor(diff / 60000);

    if (minutes < 1) return "agora";
    if (minutes < 60) return `${minutes} min`;

    const hours = Math.floor(minutes / 60);
    if (hours < 24) return `${hours} h`;

    const days = Math.floor(hours / 24);
    if (days < 30) return `${days} d`;

    const months = Math.floor(days / 30);
    if (months < 12) return `${months} meses`;

    return `${Math.floor(days / 365)} anos`;
}

dv.table(
    ["📄 Arquivo", "📅 Criada", "⏳ Modificada"],
    pages.map(p => [
        p.file.link,
        p.file.ctime.toFormat("dd/MM/yyyy"),
        relativeTime(p.file.mtime)
    ])
);
```
