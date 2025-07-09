# Todo App

A modern, full-stack todo list application built with Next.js 15, Prisma, and shadcn/ui components.

## Features

- ✅ Create, read, update, and delete todos
- ✅ Mark todos as completed/incomplete
- ✅ Edit todos inline
- ✅ Responsive design with Tailwind CSS
- ✅ Modern UI components with shadcn/ui
- ✅ SQLite database with Prisma ORM
- ✅ Docker support for easy deployment
- ✅ TypeScript for type safety

## Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript
- **UI Components**: shadcn/ui, Tailwind CSS
- **Database**: SQLite with Prisma ORM
- **Icons**: Lucide React
- **Containerization**: Docker

## Getting Started

### Prerequisites

- Node.js 20 or later
- npm or yarn
- Docker (for containerized deployment)

### Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up the database:
   ```bash
   npx prisma generate
   npx prisma migrate dev
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

### Docker Deployment

#### Using Docker directly:

1. Build the Docker image:
   ```bash
   docker build -t todo-app .
   ```

2. Run the container:
   ```bash
   docker run -p 3000:3000 todo-app
   ```

#### Using Docker Compose:

1. Build and run with Docker Compose:
   ```bash
   docker-compose up --build
   ```

2. Access the application at [http://localhost:3000](http://localhost:3000)

## Project Structure

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

## API Endpoints

- `GET /api/todos` - Fetch all todos
- `POST /api/todos` - Create a new todo
- `PUT /api/todos/[id]` - Update a todo
- `DELETE /api/todos/[id]` - Delete a todo

## Database Schema

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

## Environment Variables

- `DATABASE_URL` - Database connection string (default: `file:./dev.db`)
- `NODE_ENV` - Environment mode (development/production)

## Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE).
