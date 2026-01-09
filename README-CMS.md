# Volunteers on Wheels - Content Management System Guide

This guide explains how to use the Decap CMS (Content Management System) to create and edit news articles on the Volunteers on Wheels website.

## Accessing the CMS

1. Go to [https://www.volunteersonwheels.org.uk/admin](https://www.volunteersonwheels.org.uk/admin)
2. Click "Login with GitHub"
3. Authorize the application when prompted
4. You'll be redirected back to the CMS

**Requirements**: You must have **write access** to the GitHub repository (`volunteersonwheels/vow-website`) to use the CMS.

## Before You Start: Initial Setup Required

### Setting Up GitHub Authentication (One-time setup by admin)

The CMS uses GitHub for authentication. This means:
- Users log in with their existing GitHub accounts
- Only users with write access to the repository can use the CMS
- All changes are tracked with the user's GitHub identity

**Setup Steps**:

1. **Create a free Netlify account** at [Netlify](https://www.netlify.com)
   - Netlify provides the OAuth proxy for GitHub authentication
   - You're NOT using Netlify for hosting (GitHub Pages handles that)

2. **Import your GitHub repository to Netlify**:
   - Click "Add new site" → "Import an existing project"
   - Connect to GitHub and select the `vow-website` repository
   - Deploy settings: Leave as default
   - Click "Deploy site"

3. **Enable GitHub OAuth**:
   - Go to Site Settings → Access control → OAuth
   - Under "Authentication providers", click "Install provider"
   - Select "GitHub"
   - Click "Install"

4. **Grant repository access to team members**:
   - Go to your GitHub repository → Settings → Collaborators
   - Add users who need CMS access
   - Grant them "Write" permission (required for CMS access)

That's it! Users can now log in to `/admin` with their GitHub accounts.

## Creating a News Article

1. **Access the CMS** at `/admin`
2. Click **"News Articles"** in the sidebar
3. Click **"New News Articles"** button
4. Fill in the required fields:

### Article Fields

#### Title (Required)
- Enter a clear, descriptive headline
- Keep it under 60 characters for best SEO
- Example: "1000 Meals Delivered This Week"

#### Excerpt (Required)
- Write a brief summary (max 160 characters)
- This appears in article listings and search results
- Example: "Thanks to our amazing volunteers, we delivered over 1,000 meals to local families in need this week."

#### Featured Image (Required)
- Click "Choose an image" to upload
- **Recommended size**: 1200 x 630 pixels
- Accepted formats: JPG, PNG
- Keep file size under 1MB for fast loading

#### Publish Date (Required)
- Select the date and time for publication
- Use current date/time for immediate publication
- Can schedule for future publication

#### Author (Required)
- Select from dropdown:
  - Peter (Peter Phillips - Chair & Founder)
  - Marcus (Marcus Ardeman - Trustee)
  - Mary (Mary McDonagh - Trustee)
  - Gary (Gary Weinstein - Trustee)

#### Categories (Optional)
- Add relevant tags like:
  - News
  - Community
  - Fundraising
  - Events
  - Volunteer Stories
  - Partnership
- Press Enter after typing each category

#### Featured Article (Optional)
- Toggle ON to display prominently on homepage
- Only mark truly important articles as featured
- Limit to 2-3 featured articles at a time

#### Body (Required)
- Write your article content using the rich text editor
- Use markdown formatting:

### Markdown Formatting Guide

```markdown
# Heading 1
## Heading 2
### Heading 3

**Bold text**
*Italic text*

- Bullet point 1
- Bullet point 2

1. Numbered item 1
2. Numbered item 2

[Link text](https://www.example.com)

![Image alt text](image-url.jpg)
```

## Publishing Your Article

### Using Editorial Workflow (Recommended)

1. After filling in all fields, click **"Save"**
2. Your article is now in **"Draft"** status
3. When ready for review, drag it to **"In Review"**
4. Once approved, drag it to **"Ready"**
5. Click **"Publish"** to make it live on the website

### Direct Publishing

1. After filling in fields, click **"Publish"** → **"Publish now"**
2. Article will be live immediately
3. Changes take 1-2 minutes to appear on the website (GitHub Pages build time)

## Editing an Existing Article

1. Go to **"News Articles"** in the CMS
2. Find the article you want to edit
3. Click on it to open
4. Make your changes
5. Click **"Save"** (draft) or **"Publish"** (live update)

## Deleting an Article

1. Open the article in the CMS
2. Click the **"Delete"** button (trash icon)
3. Confirm the deletion
4. The article will be removed from the website

## Image Guidelines

### Sizing Recommendations
- **Featured images**: 1200 x 630 pixels (ideal for social sharing)
- **In-article images**: 800-1200 pixels wide
- Keep file sizes under 1MB for performance

### Image Tips
- Use high-quality photos that show VoW in action
- Include people when possible (with permission)
- Ensure good lighting and clear subjects
- Compress images before uploading (use [TinyPNG](https://tinypng.com))

## Writing Best Practices

### Article Structure
1. **Strong opening**: Hook readers in the first paragraph
2. **Clear sections**: Use headings to break up content
3. **Concise writing**: Get to the point quickly
4. **Call to action**: End with next steps (volunteer, donate, share)

### Content Ideas
- Volunteer spotlights and success stories
- Impact statistics and updates
- Partnership announcements
- Event recaps and upcoming events
- Behind-the-scenes looks at operations
- Seasonal campaigns and appeals

### SEO Tips
- Use relevant keywords naturally in title and content
- Write compelling excerpts that encourage clicks
- Add descriptive alt text to images
- Link to other relevant pages on the website

## Troubleshooting

### "Unable to access repository" or "Not Found"
- **Check repository name**: Ensure `admin/config.yml` has the correct repo name
- **Verify write access**: You must have write (not just read) access to the repository
- **Check GitHub permissions**: Go to repository Settings → Collaborators to verify your access
- **Re-authorize**: Log out of the CMS and log in again
- **Organization access**: If the repo is in an organization, you may need to grant OAuth access to the organization

### "Failed to persist entry"
- Check your internet connection
- Ensure all required fields are filled
- Try refreshing the page and re-entering content

### Changes not appearing on website
- Wait 2-3 minutes for GitHub Pages to rebuild
- Clear your browser cache (Ctrl+F5 or Cmd+Shift+R)
- Check that article is published (not in draft)

### Images not uploading
- Check file size (must be under 10MB)
- Ensure file format is JPG, PNG, or GIF
- Try a different image or compress the file

## Getting Help

If you encounter issues or need assistance:

1. Check this guide for common solutions
2. Contact the website administrator: adamr@volunteersonwheels.org.uk
3. Check the [Decap CMS Documentation](https://decapcms.org/docs/)

## Local Development (For Developers)

To test the CMS locally:

```bash
# Run Jekyll locally
jekyll serve --watch --baseurl="/vow-website"

# Access the CMS at:
http://localhost:4000/vow-website/admin
```

Note: You'll need to configure a local proxy for GitHub authentication or use Netlify's local development tools.

---

**Last Updated**: January 2026
**CMS Version**: Decap CMS 3.0
