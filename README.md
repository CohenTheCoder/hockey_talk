# Hockey Slang Translator 🏒

An interactive web app that translates between normal English and hockey slang using Claude AI.

## Features

- **Bidirectional Translation**: Convert normal English to hockey slang OR hockey slang to normal English
- **Real-time AI Translation**: Powered by Claude Sonnet 4 API
- **Comprehensive Slang Database**: Includes 80+ hockey terms from official sources
- **Interactive Examples**: Click example phrases to try them out
- **Quick Reference Guide**: Built-in glossary of common terms

## Hockey Slang Included

### Common Terms
- **Biscuit/Biscy** - Puck
- **Celly** - Celebration after a goal
- **Snipe** - Powerful, precise shot
- **Dangle** - Skillful move to get past opponent
- **Chirp** - Trash talk
- **Bar down** - Scoring by hitting puck under crossbar
- **Wheel** - Skate fast (or pick up girls)

### Players
- **Beauty/Beautician** - Cool skilled player with great personality
- **Grinder** - Hard working, physical player
- **Goon** - Player whose only talent is fighting
- **Pigeon** - Player who can't score alone
- **Pylon** - Slow defenseman who gets skated around
- **Duster** - Player who doesn't play much (collects dust)

### Equipment & More
- **Flow/Lettuce** - Long hair sticking out of helmet
- **Lip lettuce** - Mustache
- **Twig/Lumber** - Hockey stick
- **Bucket** - Helmet
- **Mitts** - Hands/gloves
- **Bird** - Girl
- **Rocket** - Really hot girl

### Special Rules
- Add "y" to words: warmup → warmy, practice → praccy
- Shorten names: McDavid → Davo, Shore → Shoresy
- "Ferda" = for the boys/team
- "The Show" = the NHL

## Files Included

1. **hockey-slang-translator.jsx** - React component version
2. **hockey-slang-translator.html** - Standalone HTML version (easiest to use!)

## How to Use

### Option 1: HTML Version (Recommended for Quick Start)
1. Open `hockey-slang-translator.html` in any modern web browser
2. That's it! No installation required.

### Option 2: React Component
1. Copy the code from `hockey-slang-translator.jsx`
2. Import it into your React project
3. Make sure you have Tailwind CSS configured
4. Add lucide-react for icons: `npm install lucide-react`

## API Setup

The app uses the Claude API. The API endpoint is configured to work without an API key when running on claude.ai.

If you want to use this elsewhere, you'll need to:
1. Get an API key from Anthropic
2. Add it to the fetch request headers:
```javascript
headers: {
  'Content-Type': 'application/json',
  'x-api-key': 'your-api-key-here',
  'anthropic-version': '2023-06-01'
}
```

## Example Translations

### English → Hockey Slang
**Input**: "He scored a beautiful goal"
**Output**: "Beauty bar down gino, bud!"

**Input**: "That was an amazing pass"
**Output**: "Silky sauce, tape to tape!"

**Input**: "The goalie made a great save"
**Output**: "The tendy absolutely stoned him!"

### Hockey Slang → English
**Input**: "Wheel, snipe, celly boys!"
**Output**: "Skate fast, shoot accurately, and celebrate, teammates!"

**Input**: "Nice flow and silky mitts on that beautician"
**Output**: "That cool player has great hair and excellent stickhandling skills"

**Input**: "Ferda! Time to crush some sandos after praccy"
**Output**: "For the team! Time to eat sandwiches after practice"

## Sources

This translator is based on official hockey slang resources from:
- [WBS Penguins Hockey Slang Guide](https://www.wbspenguins.com/blog/hockey-slang/)
- [NCAA 35 Hockey Slang Words Defined](https://www.ncaa.com/news/icehockey-men/article/35-hockey-slang-words-defined)
- [FloHockey Ultimate Guide to Hockey Slang](https://www.flohockey.tv/articles/5060128-the-ultimate-guide-to-hockey-slang)

## Technologies Used

- React 18
- Tailwind CSS
- Claude Sonnet 4 API (Anthropic)
- Lucide React (icons)

## Fun Hockey Phrases

- "Wheel, snipe, celly" - Skate fast, shoot accurately, celebrate
- "Top shelf where grandma keeps the cookies" - Upper part of the net
- "Gordie Howe hat trick" - Goal + assist + fight in one game
- "Yard sale" - Player gets hit so hard their equipment flies everywhere
- "Light the lamp" - Score a goal
- "Ferda" - For the boys/team

## License

Free to use and modify!

---

**Ferda!** 🏒

Created with Claude AI
