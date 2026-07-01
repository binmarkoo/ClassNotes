<div align="center">

# 📝 ClassNotes ✏️

### *Notizen machen, aber full-stack* 🤓

![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405e?style=for-the-badge&logo=sqlite&logoColor=white)

*Kleine App, saubere Architektur, CI/CD inklusive.* ⚙️

</div>

---

## 💭 Worum geht's?

Eine simple Notiz-App — aber richtig gemacht. Ein **React-Frontend** quatscht mit einer **ASP.NET Core REST-API**, die alles brav in **SQLite** speichert. Notizen erstellen, auflisten, verwalten. Plus GitHub Actions, die Frontend & Backend automatisch bauen. 🤖

## ✨ Features

- ✍️ Notizen erstellen & ansehen
- 💾 Persistente Speicherung via SQLite
- 📖 REST-API mit Swagger-Doku
- 🧩 Frontend & Backend getrennt deploybar
- 🤖 Automatische Build-Workflows

## 🏗️ Aufbau

| Layer | Womit |
|-------|-------|
| 🎨 Frontend | React 19 + Vite |
| ⚙️ Backend | ASP.NET Core Web API |
| 🗄️ Database | SQLite (EF Core) |
| 📖 Docs | Swagger / OpenAPI |

> 🌐 Das Backend ist per CORS so konfiguriert, dass das GitHub-Pages-Frontend fröhlich mit ihm reden darf.

## 🚀 Los geht's

### ⚙️ Backend

```bash
git clone https://github.com/binmarkoo/ClassNotes.git
cd ClassNotes/ClassNotes.Api
dotnet restore
dotnet run   # 📖 mit Swagger UI
```

### 🎨 Frontend

```bash
cd ClassNotes/frontend
npm install
npm run dev   # 👉 http://localhost:5173
```

## 📦 Das Note-Modell

```csharp
Note {
  Id: int          // 🔢
  Text: string     // ✍️
  CreatedAt: DateTime  // ⏰
}
```

## 🗂️ Projektstruktur

```
ClassNotes/
├── ⚙️ ClassNotes.Api/     # Backend
│   ├── 📦 Models/         # Note-Modell
│   ├── 🗄️ Data/           # DbContext & SQLite
│   └── 🔄 Migrations/     # EF Core Migrations
├── 🎨 frontend/           # React + Vite
│   └── 🧩 src/            # AddNoteForm, NoteList, API-Client
└── 🤖 .github/workflows/  # CI (Backend + Frontend)
