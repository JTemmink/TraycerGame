# Spelling Flappy Bird - Educational Game

Een educatief spelletje voor kinderen van 8-11 jaar gebaseerd op Flappy Bird mechanieken. Spelers vliegen door poorten met juiste/onjuiste spellingen om Nederlandse spelling te oefenen.

## Setup Instructies

1. **Installeer dependencies:**
   ```bash
   npm install
   ```

2. **Configureer environment variabelen:**
   - Kopieer `env.local.example` naar `.env.local`
   - Vul je Supabase credentials in:
     - `VITE_SUPABASE_URL` - Je Supabase project URL
     - `VITE_SUPABASE_ANON_KEY` - Je Supabase anonymous key
     - `VITE_ADMIN_EMAIL` - Admin email voor autorisatie checks

3. **Database setup:**
   - Voer `supabase/schema.sql` uit in de Supabase SQL editor
   - Stel de admin email in via: `ALTER DATABASE postgres SET app.admin_email = 'jouw-admin@email.com';`

4. **Start development server:**
   ```bash
   npm run dev
   ```

5. **Build voor productie:**
   ```bash
   npm run build
   ```

## Technologie Stack

- **Phaser.js 3.x** - Game engine
- **Vite** - Bundling en development server
- **Supabase** - Database en authenticatie

## Project Structuur

```
src/
├── scenes/          # Phaser scene classes
├── entities/        # Game entity classes (Bird, Pipe, etc.)
├── managers/        # Manager classes voor database en auth
├── utils/           # Utility functies en constants
└── main.js          # Entry point

assets/              # Game assets (sprites, sounds, fonts)
supabase/            # Database schema en migrations
```

## Development

- Het spel gebruikt responsive scaling (Phaser.Scale.FIT) voor mobiel en desktop
- Controls: Spatiebalk of tap om te springen
- Admin toegang wordt gecontroleerd via VITE_ADMIN_EMAIL environment variable

## Features

- **Authenticatie**: Supabase Auth voor gebruikersregistratie en login
- **Database**: Volledige tracking van speler statistieken en highscores
- **Responsive**: Werkt op desktop en mobiele apparaten
- **Educatief**: Focus op Nederlandse spelling voor kinderen

## License

MIT