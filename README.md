# WhatsApp-Clone
.............................................................................................................................................................................................................


## Project Plan

<section align="center">
  Developing Whatsapp Supporting with OpenAI <br/>
  <br/>
<img src="https://github.com/appicons/Whatsapp/blob/master/icons/whatsapp_194x194.png" width="90" height="90" /> <t/>
<img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/People/Handshake.webp" alt="Handshake" width="70" height="70" "/>
<img src="https://github.com/Vindyani1999/WhatsApp-Clone/assets/145743416/3a178bd9-68cf-4a5b-af22-4671ef0ac7bc" width="90" height="90" />
  </section>
<br/>
<br/>
<br/>

## Technologies to be Used

~ ReactJS - UI Design / Light & Dark Modes

~ Web Hooks - Authendication

~ HTTP Actions - Authendication

~ NextJS Middleware - Authendication

~ Convex - Database

~ OpenAI - Chat and Image generation
<br>

## Steps

1. Create a new Nextjs app
```
npx create-next-app@latest .
```
2. Shadcn is a component library
```bash
npx shadcn-ui@latest init
```

3.Updating globals.css
```bash
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
	:root {
		--background: 48, 8%, 88%; /* CHANGED */
		--foreground: 222.2 84% 4.9%;

		/* CLASSES ADDED BY US */
		--container: 0 0 100%;
		--left-panel: 203, 32%, 10%;

		--gray-primary: 216, 20%, 95%;
		--gray-secondary: 216, 20%, 95%;

		--left-panel: 100, 100%, 100%;
		--chat-hover: 180, 5%, 96%;

		--green-primary: 167, 100%, 33%;
		--green-chat: 111, 91%, 91%;
		/* CLASSES ADDED BY US */

		--card: 0 0% 100%;
		--card-foreground: 222.2 84% 4.9%;

		--popover: 0 0% 100%;
		--popover-foreground: 222.2 84% 4.9%;

		--primary: 222.2 47.4% 11.2%;
		--primary-foreground: 210 40% 98%;

		--secondary: 210 40% 96.1%;
		--secondary-foreground: 222.2 47.4% 11.2%;

		--muted: 210 40% 96.1%;
		--muted-foreground: 215.4 16.3% 46.9%;

		--accent: 210 40% 96.1%;
		--accent-foreground: 222.2 47.4% 11.2%;

		--destructive: 0 84.2% 60.2%;
		--destructive-foreground: 210 40% 98%;

		--border: 214.3 31.8% 91.4%;
		--input: 214.3 31.8% 91.4%;
		--ring: 222.2 84% 4.9%;

		--radius: 0.5rem;
	}

	.dark {
		--background: 202, 31%, 7%; /* CHANGED */
		--foreground: 210 40% 98%;

		/* CLASSES ADDED BY US: */
		--container: 202, 31%, 7%;

		--gray-primary: 202, 23%, 16%;
		--gray-secondary: 202, 22%, 17%;

		--left-panel: 203, 32%, 10%;
		--chat-hover: 202, 23%, 16%;

		--green-primary: 167, 100%, 33%;
		--green-secondary: 165, 100%, 39%;
		--green-chat: 169, 100%, 18%;

		--gray-tertiary: 203, 22%, 21%;
		/* CLASSES ADDED BY US */

		--card: 222.2 84% 4.9%;
		--card-foreground: 210 40% 98%;

		--popover: 222.2 84% 4.9%;
		--popover-foreground: 210 40% 98%;

		--primary: 210 40% 98%;
		--primary-foreground: 222.2 47.4% 11.2%;

		--secondary: 217.2 32.6% 17.5%;
		--secondary-foreground: 210 40% 98%;

		--muted: 217.2 32.6% 17.5%;
		--muted-foreground: 215 20.2% 65.1%;

		--accent: 217.2 32.6% 17.5%;
		--accent-foreground: 210 40% 98%;

		--destructive: 0 62.8% 30.6%;
		--destructive-foreground: 210 40% 98%;

		--border: 217.2 32.6% 17.5%;
		--input: 217.2 32.6% 17.5%;
		--ring: 212.7 26.8% 83.9%;
	}
}

@layer base {
	* {
		@apply border-border;
	}
	body {
		@apply bg-background text-foreground;
	}
}

/* WE ADDED => DARK MODE THIN SCROLLBAR */
@layer components {
	::-webkit-scrollbar {
		width: 8px;
	}
	::-webkit-scrollbar-thumb {
		background-color: hsl(var(--gray-primary));
		border-radius: 4px;
	}
	::-webkit-scrollbar-track {
		background-color: hsl(var(--container));
	}
}
```
4. Add the images from public folder in my repo
   
5. Addin Light/Dark mode toggle using ShadCN
   i) Install the relevent packages
   ```bash
   npm install next-themes
   ```
  ii) Add theme provider file (src > provider > theme-provider.tsx)
  ```bash
  "use client";

import * as React from "react";
import { ThemeProvider as NextThemesProvider } from "next-themes";
import { type ThemeProviderProps } from "next-themes/dist/types";

export function ThemeProvider({ children, ...props }: ThemeProviderProps) {
	return <NextThemesProvider {...props}>{children}</NextThemesProvider>;
}
  ```
iii) Wrap the {children} as below
   ```bash
<ThemeProvider attribute='class' defaultTheme='system' enableSystem disableTransitionOnChange>
	{children}
</ThemeProvider>
```

iii) Test it out 
```bash
"use client";

import { useTheme } from "next-themes";

export default function Home() {
	const { setTheme } = useTheme();

	return (
		<main className='flex min-h-screen flex-col items-center justify-between p-24'>
			<button onClick={() => setTheme("light")}>Light</button>
			<button onClick={() => setTheme("dark")}>dark</button>
			<button onClick={() => setTheme("system")}>System</button>
		</main>
	);
}
```
Test is fine? 


Congradulations!!! You are successfully setup the app's modes

