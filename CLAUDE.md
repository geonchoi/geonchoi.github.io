# Claude Code Work Log

## Project Overview
Personal academic website for Geon Choi, Postdoctoral Researcher at Com-X Laboratory, POSTECH.

## Personal Information
- **Name**: Geon Choi
- **Position**: Postdoctoral Researcher (2024 - Present)
- **Affiliation**: Com-X Laboratory, Department of Electrical Engineering, POSTECH, South Korea
- **Email**: geon.choi@postech.ac.kr
- **Supervisor**: Prof. Namyoon Lee
- **Education**: Ph.D. in Electrical Engineering, POSTECH (2018-2024)

## Website Structure & Layout
Based on reference sites:
- https://yonsei-jpark.github.io/ (main reference)
- https://sites.google.com/view/seongjoonpark
- https://sites.google.com/view/heedongdo/home

### Current Page Structure
```
/Users/choigeon/my-blog/
├── index.md (Home - no active menu, accessible via title click)
├── research/index.md (Research Areas)
├── publications/index.md (Publications)
└── sundries/index.md (Coding toolbox, snippets, resources)
```

### Navigation Menu
- **Home**: Accessible by clicking main title, no menu item
- **Research**: Research areas and interests
- **Publications**: Academic publications list
- **Sundries**: Coding toolbox, templates, utilities (inspired by Heedong Do's site)

## Key Features Implemented

### 1. Home Page (`index.md`)
- Profile section with photo and basic info
- Research interests overview
- Recent news and publications highlights
- Education and current position info
- Clean layout similar to reference sites

### 2. Research Page (`research/index.md`)
- Detailed research areas
- Current projects
- Research philosophy
- Collaboration information

### 3. Publications Page (`publications/index.md`)
- Comprehensive publication list including:
  - Journal articles
  - Conference papers
  - Patents (Korean and US)
  - Domestic and international conferences
- Organized chronologically with proper formatting

### 4. Sundries Page (`sundries/index.md`)
- MATLAB and Python code snippets for channel coding
- LaTeX templates for IEEE papers
- Research tools and software recommendations
- Configuration files (VS Code, Git)
- Quick reference materials
- Mathematical notation guide

## Design & Styling Updates

### Layout Modifications (`_sass/_layout.scss`)
- Updated header styling with cleaner background and subtle shadow
- Modified navigation styling with better typography
- Removed text-transform: uppercase for cleaner look
- Updated link colors and hover effects

### Site Configuration (`_config.yml`)
- Updated site title to "Geon Choi"
- Updated email to geon.choi@postech.ac.kr
- Updated description for SEO

## Removed Components
- Deleted unnecessary directories: `/talks`, `/group`, `/teaching`
- These were removed as they're not needed for a postdoc researcher profile

## Technical Notes

### Jekyll Structure
- Uses default Jekyll theme with custom SCSS modifications
- Profile image: `assets/images/profile.JPG`
- Main stylesheet: `assets/main.scss` (imports `voyager` theme)

### Key Files Modified
1. `index.md` - Main homepage
2. `_config.yml` - Site configuration
3. `_sass/_layout.scss` - CSS styling updates
4. `research/index.md` - Research page
5. `publications/index.md` - Publications (contains actual publication data)
6. `sundries/index.md` - Utility page with code snippets

## Development Commands
```bash
# To run Jekyll locally
bundle exec jekyll serve

# To build the site
bundle exec jekyll build
```

## Important Notes for Future Work
1. The user is a postdoctoral researcher (not a student, not a professor)
2. Com-X Laboratory website: https://comx.postech.ac.kr/
3. Main reference site layout: https://yonsei-jpark.github.io/
4. Publications list in `publications/index.md` contains real publication data
5. Profile image is located at `assets/images/profile.JPG`
6. Email contacts should use geon.choi@postech.ac.kr (institutional email)

## Future Enhancements to Consider
- Add Google Scholar and LinkedIn links to profile
- Implement responsive design improvements
- Add more code snippets to Sundries based on user's research
- Consider adding a CV download link
- Update publications list as new papers are published

---
*Last updated: {{ site.time | date: "%Y-%m-%d %H:%M:%S" }}*