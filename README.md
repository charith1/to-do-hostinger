# Todo App

A modern, full-stack todo list application built with Next.js 15, Prisma, and shadcn/ui components.

## 🎯 Features

- ✅ Create, read, update, and delete todos
- ✅ Mark todos as completed/incomplete
- ✅ Edit todos inline
- ✅ Responsive design with Tailwind CSS
- ✅ Modern UI components with shadcn/ui
- ✅ SQLite database with Prisma ORM
- ✅ Docker support for easy deployment
- ✅ TypeScript for type safety
- 🐳 **Available on GitHub Container Registry**

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript
- **UI Components**: shadcn/ui, Tailwind CSS
- **Database**: SQLite with Prisma ORM
- **Icons**: Lucide React
- **Containerization**: Docker
- **Registry**: GitHub Container Registry (ghcr.io)

## 🚀 Quick Start

### Using Docker (Recommended)

**Pull and run from GitHub Container Registry:**
```bash
# Latest version
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:latest

# Specific version
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:v1.0.0
```

**Using Docker Compose:**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker-compose up
```

### Local Development

**Prerequisites:**
- Node.js 20 or later
- npm or yarn

**Setup:**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
npm install
npx prisma generate
npx prisma migrate dev
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📦 Container Registry

**GitHub Container Registry:**
- Repository: `ghcr.io/charith1/to-do-hostinger`
- Tags available: `latest`, `v1.0.0`
- Size: 331MB
- Base: Node.js 20 Alpine Linux

**Pull commands:**
```bash
# Pull latest
docker pull ghcr.io/charith1/to-do-hostinger:latest

# Pull specific version
docker pull ghcr.io/charith1/to-do-hostinger:v1.0.0
```

## 🏗️ Build from Source

**Local Docker build:**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker build -t todo-app .
docker run -p 3000:3000 todo-app
```

## 📁 Project Structure

```
├── src/
│   ├── app/
│   │   ├── api/todos/          # API routes for todo operations
│   │   ├── globals.css         # Global styles
│   │   ├── layout.tsx          # Root layout
│   │   └── page.tsx            # Main todo app page
│   ├── components/ui/          # shadcn/ui components
│   └── lib/
│       ├── prisma.ts           # Prisma client setup
│       └── utils.ts            # Utility functions
├── prisma/
│   ├── schema.prisma           # Database schema
│   └── migrations/             # Database migrations
├── Dockerfile                  # Docker configuration
├── docker-compose.yml         # Docker Compose configuration
└── package.json               # Dependencies and scripts
```

## 🔌 API Endpoints

- `GET /api/todos` - Fetch all todos
- `POST /api/todos` - Create a new todo
- `PUT /api/todos/[id]` - Update a todo
- `DELETE /api/todos/[id]` - Delete a todo

## 🗄️ Database Schema

```prisma
model Todo {
  id          Int      @id @default(autoincrement())
  title       String
  description String?
  completed   Boolean  @default(false)
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}
```

## 🌍 Environment Variables

- `DATABASE_URL` - Database connection string (default: `file:./dev.db`)
- `NODE_ENV` - Environment mode (development/production)

## 📜 Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## 🚀 Deployment Options

### **1. Docker Hub / Registry**
```bash
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:latest
```

### **2. Vercel**
```bash
npm run build
# Deploy to Vercel
```

### **3. Railway**
```bash
# Connect GitHub repository to Railway
# Automatic deployment on push
```

### **4. Self-hosted**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker-compose up -d
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and commit: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🔗 Links

- **Repository**: [GitHub](https://github.com/charith1/to-do-hostinger)
- **Container Registry**: [GitHub Packages](https://github.com/charith1/to-do-hostinger/pkgs/container/to-do-hostinger)
- **Issues**: [Report bugs](https://github.com/charith1/to-do-hostinger/issues)

---

**Built with ❤️ using Next.js 15, Prisma, and shadcn/ui**
