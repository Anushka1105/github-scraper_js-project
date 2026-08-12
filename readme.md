
  

# Github Profile Scraper

  

A small client-side web app that fetches and displays public GitHub profile information for a given username using the GitHub REST API. It provides a simple UI with a dark/light toggle and shows key profile fields (followers, following, public repos, bio, company, location, avatar, etc.).

  

## Demo

Open index.html in any browser to try it locally:

- Enter a GitHub username (for example: `torvalds`, `octocat`) and click "Search".

- Use the moon/sun icon (top-right) to toggle dark/light mode.

  

## Stack

- Language(s): HTML, CSS, JavaScript

- Framework / runtime: Browser (vanilla JS)

- Notable libraries: Remix Icon (CDN for icons)

  

## How it works

The UI sends a GET request to the public GitHub API endpoint:

`https://api.github.com/users/<username>`

  

The returned JSON is used to populate the page DOM with:

- followers, following, public_repos, bio, company, twitter_username, created_at, login, id, name, location

- avatar is shown using the avatars.githubusercontent.com URL with the user's id

  

## Files

```

index.html — main UI and markup

script.js — client-side logic: fetch GitHub API and update DOM; dark mode toggle

style.css — page styling and layout

```

  

## How to run (shortest path)

1. Clone the repo:

```bash

git clone https://github.com/Anushka1105/github-scraper_js-project.git

cd github-scraper_js-project

```

2. Open index.html in your browser:

- Double-click index.html or

- Serve it from a simple static server (recommended to avoid some browser restrictions):

```bash

# Python 3

python3 -m http.server 8000

# or using npm http-server

npx http-server -p 8000

```

- Then open http://localhost:8000 in your browser.

  

## Usage

- Enter a GitHub username in the input field and click "Search".

- The app shows public profile data (some fields may be blank if not public).

- Toggle dark/light mode with the icon in the top-right.

  

## Notes & limitations

- Uses the public GitHub API without authentication. Unauthenticated requests are rate-limited (typically 60 requests per hour per IP). For higher rate limits, you must proxy requests through a server using a GitHub token (do NOT embed a personal token in client-side code).

- Some profile fields (email, company, twitter_username, location) can be null or empty depending on user privacy/settings.

- Error handling is minimal: if a username doesn't exist or the API fails, the UI does not currently show a user-friendly error message.

- The displayed `created_at` value is the raw ISO timestamp — it is not formatted for readability.

  

## Contributing

Contributions, issues and feature requests are welcome. If you'd like to add the README to the repository as a commit/PR, I can prepare a patch/PR for you.

  

## License

No license file is provided in the repo. If you'd like, add an open-source license such as MIT by creating a LICENSE file.
