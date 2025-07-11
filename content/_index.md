---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: "Hi! I am a first-year master's student in ECE at the University of Washington, currently working as a research assistant at the Ubiquitous Computing Lab. Before coming to UW, I completed my undergraduate degree at the <a href=\"https://www.sustech.edu.cn/en/\">Southern University of Science and Technology</a>, where I was fortunately mentored by <a href=\"https://scholar.google.co.uk/citations?user=jWmF7IQAAAAJ&hl=en\">Prof. Guoping Liu</a> and <a href=\"https://scholar.google.com/citations?user=sNve2YAAAAAJ&hl=zh-CN\">Prof. Xing Cheng</a>. "
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/CV_Zach Hao.pdf
    design:
      css_class: fancy-hero dark
      background:
        color: '#0a192f'
        image:
          # Add your image background to `assets/media/`.
          filename: Space.png
          filters:
            brightness: 0.7
          size: cover
          position: center
          parallax: true
      avatar:
        size: xl
        border: true
        shadow: true
        shape: circle
  - block: markdown
    content:
      title: '📚 My Research'
      subtitle: ''
      text: |-
        My research interests include Embedded systems, AIoT, and Machine Learning. 
        
        Besides, I'm genuinely interested in exploring how technology and business can be integrated to address real-world challenges and contribute positively to society.

        Please reach out to collaborate 😃
    design:
      columns: '1'

  # - block: collection
  #   id: papers
  #   content:
  #     title: Featured Publications
  #     filters:
  #       folders:
  #         - publication
  #       featured_only: true
  #   design:
  #     view: article-grid
  #     columns: 2

  - block: collection
    content:
      title: Recent Projects
      text: ""
      filters:
        folders:
          - project
        exclude_featured: false
    design:
    #   spacing:
    # # Customize the section spacing. Order is top, right, bottom, left.
    #   padding: ['20px', '0', '20px', '0']
      view: article-grid
      columns: 2

  # - block: markdown
  #   content:
  #     title: 'Work Experience'
  #     subtitle: ''
  #     text: |-
  #       **Founder**  
  #       Shenzhen Suishi Technology Co, Ltd.  
  #       *April 2023 – June 2024*

  #       - 🌐 **Platform Development**: Launched a comprehensive campus offer platform, partnering with major platforms (Meituan, Taobao, Jingdong) to provide college students with exclusive discounts on food, entertainment, and online shopping.  


  #       - 🎨 **User Experience & Interface Design**: Mapped user journeys to understand user needs, designed and implemented the front end of a WeChat mini-program using JavaScript and Wechat Devtools, ensuring a smooth and intuitive user experience.  

  #       - 📊 **Data Analysis & Strategic Planning**: Used Tableau for data visualization, analyzing user trends and behaviors to inform financial management and company strategy. Implemented UI enhancements and functionality optimizations in mini-programs to keep users engaged.  

  #       - 📝 **WeChat Public Account Operation & Content Creation**: Created and managed content for the company's WeChat public account, focusing on topics relevant to college student growth and education. Authored a popular article on university student development, achieving over 68,000 views on a single post. 

    # design:
    #   columns: '1'
  # - block: collection
  #   id: talks
  #   content:
  #     title: Recent & Upcoming Talks
  #     filters:
  #       folders:
  #         - event
    # design:
    #   view: article-grid
    #   columns: 1
  - block: collection
    id: news
    content:
      title: Recent News
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: post
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: date-title-summary
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]

  - block: cta-card
    demo: true # Only display this section in the Hugo Blox Builder demo site
    content:
      title: 👉 Build your own academic website like this
      text: |-
        This site is generated by Hugo Blox Builder - the FREE, Hugo-based open source website builder trusted by 250,000+ academics like you.

        <a class="github-button" href="https://github.com/HugoBlox/hugo-blox-builder" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star HugoBlox/hugo-blox-builder on GitHub">Star</a>

        Easily build anything with blocks - no-code required!
        
        From landing pages, second brains, and courses to academic resumés, conferences, and tech blogs.
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700"
        css_style: ""
---
