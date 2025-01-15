# Ski Conditions Dashboard

## The Problem

Whenever I had a desire to go skiing, there were several checks in order to determine the conditions, weather, etc. These checks included:

1. Weather — how cold? How much snow is expected in the days leading up to the skiing?
2. Hill Conditions — What's the grooming at the hill like? How many lifts are open?
3. Nordic Trails — Any blog post entries for the locations I XC ski at? Are the trails set?

To answer these questions, this meant visiting multiple websites and filtering through irrelevant information. It would be much quicker if those sites offered an RSS feed, but alas, that's far in the rear view mirror.

## The Solution

This repository is part of a two-repository solution that creates a dashboard compiling ski-related data into a single view. This repository (`ski-conditions-website`) provides the frontend dashboard, while the companion repository [`ski-conditions-data`](https://github.com/stosento/ski-conditions-data) handles the data collection.

The dashboard displays:
- Weather forecasts with snow predictions
- Nordic ski trail conditions
- Nubs Nob operational status and conditions

## Technical Details

This is a simple static website built with modern web technologies:

### Technologies Used
- HTML5 for structure
- Tailwind CSS (via CDN) for styling
- Vanilla JavaScript for functionality

### Key Features
- Responsive design (mobile and desktop layouts)
- Auto-refresh every 5 minutes
- Loading states and error handling
- Special highlighting for snow conditions
- Graceful handling of missing data

### How It Works

The website:
1. Fetches data from the conditions.json file in the data repository
2. Processes and displays the information in an easy-to-read format
3. Updates automatically to ensure fresh data
4. Provides visual feedback for loading and error states

## Hosting Details

The site is hosted using GitHub Pages, which:
- Automatically deploys when changes are pushed to main
- Serves the static files via GitHub's CDN
- Provides reliable, free hosting

You can view the live dashboard at: `https://stosento.github.io/ski-conditions-website`

## Local Development

1. Clone the repository
```bash
git clone https://github.com/stosento/ski-conditions-website.git
cd ski-conditions-website
```

2. Serve the files locally
```bash
# Using Python
python -m http.server 8000

# Or using Node.js http-server
npx http-server
```

3. Visit `http://localhost:8000` in your browser

## Project Structure

```
ski-conditions-website/
└── index.html    # Contains all HTML, CSS (via Tailwind), and JavaScript
```

## Related Projects

This repository works in conjunction with [`ski-conditions-data`](https://github.com/stosento/ski-conditions-data), which handles all the data collection and processing. The data repository uses GitHub Actions to regularly update the conditions data that this dashboard displays.
