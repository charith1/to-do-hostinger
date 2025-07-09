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
- 🐳 **Multi-platform Docker images (AMD64 + ARM64)**
- 📦 **Available on GitHub Container Registry**

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript
- **UI Components**: shadcn/ui, Tailwind CSS
- **Database**: SQLite with Prisma ORM
- **Icons**: Lucide React
- **Containerization**: Docker (Multi-platform)
- **Registry**: GitHub Container Registry (ghcr.io)

## 🚀 Quick Start

### Using Docker (Recommended)

**Pull and run from GitHub Container Registry:**
```bash
# Latest version (supports both AMD64 and ARM64)
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:latest

# Specific version
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:v1.0.1
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
- Tags available: `latest`, `v1.0.1`
- **Platforms**: `linux/amd64`, `linux/arm64`
- Size: ~331MB per platform
- Base: Node.js 20 Alpine Linux

**Pull commands:**
```bash
# Pull latest (multi-platform)
docker pull ghcr.io/charith1/to-do-hostinger:latest

# Pull specific version
docker pull ghcr.io/charith1/to-do-hostinger:v1.0.1
```

## 🏗️ Build from Source

**Local Docker build:**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker build -t todo-app .
docker run -p 3000:3000 todo-app
```

**Multi-platform build:**
```bash
# Create a new builder instance
docker buildx create --name multiplatform --use

# Build for multiple platforms
docker buildx build --platform linux/amd64,linux/arm64 \
  -t ghcr.io/charith1/to-do-hostinger:latest \
  --push .
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
├── Dockerfile                  # Multi-platform Docker configuration
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

### **1. Docker Registry (Multi-platform)**
```bash
# Works on both Intel/AMD64 and ARM64 systems
docker run -p 3000:3000 ghcr.io/charith1/to-do-hostinger:latest
```

### **2. Docker Compose**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker-compose up
```

### **3. Vercel**
```bash
npm run build
# Deploy to Vercel via GitHub integration
```

### **4. Railway/Render**
- Connect GitHub repository
- Automatic deployment on push

### **5. Self-hosted VPS**
```bash
git clone https://github.com/charith1/to-do-hostinger.git
cd to-do-hostinger
docker-compose up -d
```

## 🔧 Architecture Support

**Supported Platforms:**
- ✅ **Linux AMD64** (Intel/AMD processors)
- ✅ **Linux ARM64** (Apple Silicon, ARM processors)
- ✅ **Automatic platform detection**

**Multi-platform Benefits:**
- Works on both Intel and ARM-based systems
- Optimized builds for each architecture
- No compatibility issues across different hardware

## 🐛 Troubleshooting

**"no matching manifest for linux/amd64" error:**
- This is resolved in v1.0.1+ with multi-platform support
- Use: `docker pull ghcr.io/charith1/to-do-hostinger:latest`

**Permission denied errors:**
- Ensure Docker daemon is running
- Check if the image is public on GitHub Container Registry

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

## 📋 Version History

- **v1.0.1** - Multi-platform Docker support (AMD64 + ARM64)
- **v1.0.0** - Initial release with single-platform Docker image

---

**Built with ❤️ using Next.js 15, Prisma, and shadcn/ui**
