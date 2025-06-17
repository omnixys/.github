// theme.md – Omnixys UI Design Tokens

## 🎨 Farbdefinitionen im Theme

Die Farben orientieren sich an den Branding-Vorgaben aus `OMNIXYS-BRANDING.md` und werden dynamisch über den `mode` ("light" | "dark") gesteuert.

### 🌞 Light Mode
```ts
background: {
  default: '#F8F8FC',
  paper: '#FFFFFF'
},
primary: {
  main: '#6A4BBC'
},
secondary: {
  main: '#4E3792'
},
success: {
  main: '#A3E635'
},
error: {
  main: '#F87171'
},
text: {
  primary: '#312E81',
  secondary: '#6B7280'
}
```

### 🌙 Dark Mode
```ts
background: {
  default: '#121212',
  paper: '#1E1E1E'
},
primary: {
  main: '#6A4BBC'
},
secondary: {
  main: '#4E3792'
},
success: {
  main: '#A3E635'
},
error: {
  main: '#F87171'
},
text: {
  primary: '#EDEDED',
  secondary: '#BFBFC7'
}
```

---

## 🔤 Typografie
```ts
typography: {
  fontFamily: 'Inter, Poppins, sans-serif',
  h1: { fontFamily: 'Poppins', fontWeight: 700 },
  h2: { fontFamily: 'Poppins', fontWeight: 700 },
  button: { fontFamily: 'Poppins', fontWeight: 500 },
}
```

---

## 🧩 Abhängigkeiten
- `@mui/material` (ThemeProvider, CssBaseline)
- `next/font/google` → Inter + Poppins
- `createTheme` aus MUI

---

## 📦 Dateistruktur (Beispiel)
```
src/
├── theme/
│   ├── theme.ts            # themeFactory(mode)
│   ├── ColorModeContext.tsx # toggleColorMode + Provider
│   └── theme.md            # Design Tokens (du liest gerade)
```

---

## ✅ Empfehlung zur Nutzung
- Nutze `useTheme()` aus MUI in Komponenten
- Ersetze harte Farben durch Theme-Farben wie `theme.palette.background.paper`
- Komponentenspezifisch kannst du z. B. `primary.light`, `action.hover`, etc. ergänzen

| Farbe        | Vorher    | Theme-konform                    |
| ------------ | --------- | -------------------------------- |
| Notfall-Rand | `#F87171` | `theme.palette.error.main`       |
| Notfall-HG   | `#FFF5F5` | `theme.palette.error.light`      |
| Standard-HG  | `"white"` | `theme.palette.background.paper` |


---

## 🧪 Beispiel: Light/Dark Mode Umschaltung
```tsx
const theme = useTheme();
<Box bgcolor={theme.palette.background.paper} color={theme.palette.text.primary}>
  ...
</Box>


