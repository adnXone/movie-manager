# 🎬 movie-manager

**✨ Proactive AI agent for organizing movies in Obsidian.**

Delivers personalized recommendations, manages watchlist/seen lists, and learns from your cinematic tastes. Features structured templates, mandatory YouTube trailers, and post-viewing feedback systems.

---

## 🚀 Features

- **Automated watchlist & seen list tracking**
- **Personalized recommendations** based on your cinematic profile
- **Full Obsidian integration** (WikiLinks, Templates)
- **Structured post-viewing reflections**
- **+1/-1 feedback system** for continuous learning
- **Ready-to-use templates**
- **Compatible with OpenClaw & ClawHub ecosystems**

---

## 📁 Structure

```
movie-manager/
├── README.md                     # This file
└── skill/
    └── movie-manager/
        ├── SKILL.md             # Skill specification
        ├── README.md            # Detailed documentation
        └── package.json         # Metadata
```

---

## 🛠️ Installation

### Via ClawHub (Recommended)
```bash
clawhub install movie-manager
```

### Via GitHub
```bash
cd ~/.openclaw/workspace
git clone https://github.com/adnXone/movie-manager.git
cd movie-manager/skill/movie-manager
# Install into OpenClaw skills directory
```

---

## 🎯 Use Cases

- **Movie enthusiasts** who want to organize their collection
- **OpenClaw users** looking for personalized AI recommendations
- **Obsidian power users** wanting structured data management
- **Content creators** tracking watch history and preferences

---

## 💡 How It Works

1. **Recommend**: AI suggests films based on your profile
2. **Track**: Files stored in `watchlist/` with metadata
3. **Watch**: Mark as seen, add reflections and ratings
4. **Learn**: System adapts to your preferences over time

---

## 📝 Template Example

```markdown
# {Title} ({Year})
![Poster]({URL})

- **Rating**: ⭐ {IMDb/RT}
- **Actors**: [[Actor1]], [[Actor2]]
- **Genre**: [[Genre]]
- **Trailer**: [Link](...)

### 💡 Why it fits you
{Personalized reasoning}

### ✍️ Post-Watch
- **Memorable Scene**: 
- **Personal Rating**: ⭐ {1-10}
- **Feedback**: +1 / -1
```

---

## 🔗 Links

- **GitHub**: [github.com/adnXone/movie-manager](https://github.com/adnXone/movie-manager)
- **Skill Location**: `skill/movie-manager/`
- **OpenClaw Registry**: [clawhub.ai](https://clawhub.ai)

---

## 📄 License

MIT License - See `LICENSE` file in skill directory.

---

**Built with ❤️ for the OpenClaw community.**
