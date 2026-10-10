# 原工程 22 个 `promptData` 配方

来源：`work/Top22comic-source/constants.ts`，Top22comic commit `30e377e816d8e39a70671f482aa2b4c1aece78c8`。以下逐项保留原工程的作者标签、作品标签及 `promptData` 字段和值；它们是原工程的结构化风格指令，不是 22 条完整独立的自然语言 prompt。

原工程的 `services/geminiService.ts` 将每项字段组装进同一套提示框架：要求保持用户脸部身份线索，声明 `Target Style`，依次写入线条、明暗、造型、配色、可选材质与构图、氛围及 `Avoid`。随后把提示词和照片交给 Gemini `gemini-3-pro-image-preview`。迁移至 GPT Image 2.5 时，应把下列每个已定义字段都改写成自然语言并保留其视觉意图；不要把一整项缩成通用的“漫画头像”或只保留两三个关键词。把原 `negative` 约束并入自然语言排除要求，再附加 Skill 中的通用降噪约束。原工程未定义的材质或构图字段不要臆造。

## 少年 / 青年漫画方向

### 01. 荒木飞吕彦｜JoJo 的奇妙冒险
- `lineModulation`: High / Thick Ink / Variable Pressure. Use heavy, deliberate black ink outlines with varying thickness.
- `shading`: Dense Hatching on Cheeks & Neck / High Contrast. 'Araki-style' shading lines (dense parallel hatching) specifically on cheekbones and nose bridge.
- `anatomy`: 8-9 Heads / Sculptural Definition / Angular Jaw. Chiseled, statue-like appearance, sharp angular jawlines, intensely detailed eyes with thick lashes.
- `colorPalette`: Psychedelic / Non-naturalistic (Cyan, Magenta, Gold). Violet skin tones, golden skies, neon highlights.
- `vibe`: Bizarre, intense, high-fashion baroque aesthetic, dynamic dramatic posing.
- `negative`: Soft, round, cute, low contrast, realistic skin texture

### 02. 尾田荣一郎｜海贼王 (One Piece)
- `lineModulation`: Loose / Organic / Wobbly / Energetic. Ink lines with a slight 'wobbly' hand-drawn organic feel, avoiding stiff vectors.
- `shading`: Minimal on skin / Scribble texture on backgrounds.
- `anatomy`: Caricatured / Wide Mouths / Circular Eyes / Spindly Limbs. Exaggerated proportions, thin limbs, large hands/feet, big grin.
- `colorPalette`: Tropical / Saturated / Copic Marker Texture. Bright primary colors (blues, reds, yellows).
- `vibe`: Adventurous, chaotic, fun, dynamic shonen energy, whimsical.
- `negative`: Serious, dark, gritty, realistic proportions, stiff

### 03. 鸟山明｜龙珠 / 阿拉蕾
- `lineModulation`: Uniform / Crisp / Mechanical Precision. Incredibly crisp, clean black outlines with uniform thickness.
- `shading`: Hard-edge Cel-shading / Blocky Shadows. High contrast between light and shadow, no gradients.
- `anatomy`: Geometric Muscles / Angular Eyes / Compact. Muscles as interlocking geometric blocks (square pecs), sharp triangular eyes.
- `colorPalette`: High Contrast / Primary Colors / Clean.
- `vibe`: Retro 90s anime, powerful, clean, industrial design aesthetic.
- `negative`: Sketchy, messy, painterly, soft focus

### 04. 井上雄彦｜浪客行 / 灌篮高手
- `lineModulation`: Variable (G-Pen to Brush) / Calligraphic. Combine precise pen work for features with expressive traditional Japanese Sumi-e ink brush strokes.
- `shading`: Sumi-e Ink Wash + Hatching / Chiaroscuro. Deep high-contrast shading.
- `anatomy`: Hyper-Realistic / Emotive / Detailed Pores & Sweat. Strictly realistic proportions, intense soulful expression.
- `colorPalette`: Black and White Ink Wash aesthetics or muted earth tones if color.
- `texture`: Visible dry-brush effects, bristle marks, and ink splatters.
- `vibe`: Serene, meditative, gritty realism, philosophical.
- `negative`: Cartoonish, flat, vector art, bright neon colors

### 05. 三浦建太郎｜烙印战士 (Berserk)
- `lineModulation`: Extremely Fine / High Frequency. Simulate the look of a detailed copperplate etching.
- `shading`: Multi-directional Cross-Hatching / Micro-Detailing. Obsessively detailed cross-hatching to create volume without solid blacks.
- `anatomy`: Gritty Realism / Heavy / Textural. Intense shadowed eyes, dramatic lighting.
- `colorPalette`: Dark Fantasy / Ominous / Dense. High-contrast monochrome or deep blood reds and shadows.
- `vibe`: Heavy, oppressive, ominous, atmospheric, Gustave Dore engraving style.
- `negative`: Clean, empty, white background, kawaii, simple

### 06. 久保带人｜死神 (Bleach)
- `lineModulation`: Sharp / Angular / Cutting. Sharp, angular, 'cutting' ink lines.
- `shading`: Solid Blacks vs Stark Whites / No Mid-tones. Large areas of solid black (Beta) against stark white skin.
- `anatomy`: Elongated / Fashion Model Proportions / Sharp Chin. Angular nose, cool and confident expression.
- `colorPalette`: Monochrome with occasional high-impact color. Minimalist.
- `composition`: Complete omission of background (pure white negative space).
- `vibe`: Effortlessly cool, sleek, modern shonen, streetwear aesthetic.
- `negative`: Cluttered, textured, messy, round features

### 07. 村田雄介｜一拳超人
- `lineModulation`: Polished / Digital Ink / Speed Lines. Incredibly polished, clean digital-ink aesthetic.
- `shading`: High-fidelity Rendering / Metallic Sheen. Sophisticated rendering with metallic textures and rim lighting.
- `anatomy`: Anatomical Perfection / Heroic Build. Highly detailed musculature.
- `composition`: Dynamic wide-angle lens effect (fish-eye distortion) / Extreme foreshortening.
- `colorPalette`: Vibrant, high budget animation feel.
- `vibe`: Heroic, cinematic, blockbuster action manga.
- `negative`: Flat, static, rough, sketchy

### 08. 贰瓶勉｜Blame! / 希德尼娅的骑士
- `lineModulation`: Thin / Scratchy / Architectural. Mimic etched metal or dirty concrete.
- `shading`: Heavy shadows around eyes, high contrast.
- `anatomy`: Pale / Stoic / Heavy Eye Shadow. Emotionless expression, pale skin.
- `texture`: Grime, concrete, cables, chaotic pipes.
- `colorPalette`: Desolate, atmospheric, hard sci-fi, monochrome or cold tones.
- `vibe`: Lonely, vast scale, brutalist megastructure.
- `negative`: Warm, happy, clean, organic nature

### 09. 藤本树｜电锯人
- `lineModulation`: Rough / Sketchy / Unpolished. Pencil-like textures, retaining a hand-drawn aesthetic.
- `shading`: Flat Greys / Messy Hatching. Avoid polished gradients.
- `anatomy`: Slouching / Apathetic Expression / Concentric Eyes. Deadpan or slightly manic, distinct eyes (concentric rings).
- `colorPalette`: Cinematic / Chaotic / Raw. Flat colors.
- `vibe`: Chaotic, gritty, emotional, alternative shonen, indie film framing.
- `negative`: Polished, beautiful, shiny, perfect anatomy

### 10. 伊藤润二｜漩涡 / 富江
- `lineModulation`: Fine / Clinical / Precise ink lines.
- `shading`: Stark black and white, cold atmosphere.
- `anatomy`: Pale Beauty vs. Body Horror. Pale smooth skin, intense staring eyes with detailed lashes.
- `texture`: Spirals / Rot / Veins / Dense Lines. Subtle grotesque textures encroaching on the frame.
- `colorPalette`: Monochrome, pale, eerie.
- `vibe`: Eerie, unsettling, uncanny valley realism, claustrophobic.
- `negative`: Warm, safe, cheerful, cartoony

### 11. 石田翠｜东京喰种
- `lineModulation`: Chaotic paint strokes mixed with sharp ink.
- `shading`: Digital watercolor texture.
- `anatomy`: Melancholic expression, stylized features.
- `colorPalette`: Neon accents on black / Shattered glass aesthetic. High saturation purple/pink/blue on dark.
- `vibe`: Dark melancholic atmosphere, emotional, digital painting style.
- `negative`: Flat, solid colors, cheerful

### 12. 林田球｜异兽魔都 (Dorohedoro)
- `lineModulation`: Thick ink lines, messy but detailed.
- `shading`: Heavy shading, masking tape residue texture.
- `anatomy`: Strong / Thick / Wild.
- `texture`: Grimy, sludge aesthetic, noise, ink spots.
- `colorPalette`: Muddy, punk fantasy, dark.
- `vibe`: Chaos, sludge punk, gritty.
- `negative`: Clean, shiny, digital perfection

## 少女 / 女性漫画方向

### 13. 高桥留美子｜犬夜叉 / 乱马½
- `lineModulation`: Medium / Constant / Curved. Simple, clean, continuous curved black lines.
- `shading`: Cel-style, minimal weight variation.
- `anatomy`: Round Cheeks / Small Nose / Large Eyes (Small Pupils). Tiny dot/tick nose, soft rounded structure.
- `texture`: Hair: Distinct white zig-zag band of highlight across the crown.
- `colorPalette`: Vintage 80s anime color palette, slightly saturated warm tones.
- `vibe`: Playful, classic 90s manga, charming, slapstick comedy.
- `negative`: Sharp, angular, realistic, detailed shading

### 14. 武内直子｜美少女战士
- `lineModulation`: Very Thin / Delicate / Floating / Wispy.
- `shading`: Soft watercolor coloring, transparent.
- `anatomy`: 10+ Heads / Spindly / Fashion Illustration. Exaggeratedly elongated limbs and neck, large sparkling eyes.
- `colorPalette`: Watercolor / Pastel / Iridescent / Ethereal. Soft pastels, golds, whites.
- `composition`: Art Nouveau inspired floral patterns, floating beads, celestial motifs.
- `vibe`: Magical, romantic, high-fashion illustration, dreamy.
- `negative`: Heavy lines, black shadows, gritty, muscular

### 15. CLAMP｜百变小樱 / xxxHolic
- `lineModulation`: Intricate / Decorative / Flowing. Varying from thin detail to thick structural lines.
- `shading`: High contrast (xxxHolic style) or soft (Sakura style).
- `anatomy`: Elongated / Stylized / Clamp Anatomy. Slender frame, stylized limbs.
- `composition`: Filled with dynamic floating elements like feathers, petals, magic circles.
- `colorPalette`: High Detail / Jewelry / Frills. Gothic romance colors or vivid magical colors.
- `vibe`: Gothic romance, magical, dramatic, visually dense, 'Horror Vacui' of beauty.
- `negative`: Empty background, simple clothes, realistic proportions

### 16. 矢泽爱｜NANA / 天堂之吻
- `lineModulation`: Sharp / Fashion Sketch Style. Sharp, thin, stylish ink lines.
- `shading`: Minimal shading, focus on pattern and texture.
- `anatomy`: Extremely Slender / Big Heads / Thin Necks. Large eyes with long sharp lashes, distinct lipstick.
- `texture`: Plaid / Leather / Piercings. Vivienne Westwood aesthetic.
- `colorPalette`: Punk Rock / Edgy / Cool.
- `vibe`: Edgy, cool, dramatic, rebellious, shojo-punk.
- `negative`: Soft, cute, traditional, plain clothes

### 17. 荒川弘｜钢之炼金术师
- `lineModulation`: Solid / Medium Thickness / Confident. Clean black outlines.
- `shading`: Clean / Volumetric / Metallic. Defining volume and weight.
- `anatomy`: Round Faces / Sturdy Bodies / Grounded. Distinctive simple but expressive eye shape.
- `colorPalette`: Earnest / Steampunk / Solid. Earth tones and metallics.
- `vibe`: Earnest, grounded shonen manga, functional design.
- `negative`: Wispy, floating, fragile, hyper-detailed eyes

### 18. 羽海野千花｜蜂蜜与四叶草
- `lineModulation`: Soft / Shaky / Warm / Hand-drawn. Gentle lines, avoiding sharp vectors.
- `shading`: Simulate watercolor or soft crayon textures.
- `anatomy`: Soft / Cute / Expressive Mouths. Soft rounded features, 'watery' eyes.
- `colorPalette`: Pastel / Hazy / Cream & Pink / Soft Gradient.
- `vibe`: Warm, emotional, dreamy, indie slice-of-life, nostalgic.
- `negative`: Hard lines, dark shadows, aggressive, sharp

### 19. 安野梦洋子｜恶女花魁 / 魔女的考验
- `lineModulation`: Thick / Bold / Woodblock Print Style. Variable-width ink lines with 'hooked' endings.
- `shading`: Flat / Retro Florals / Stripes.
- `anatomy`: Stylized Lips / Big Eyes / Angular. Distinctively decorated eyes.
- `colorPalette`: Pop Art / Vibrant / Ukiyo-e Inspired. Saturated, retro-pop.
- `vibe`: Stylish, bold, retro-modern, fashionable.
- `negative`: Subtle, realistic, sketch, pastel

### 20. 板垣巴留｜BEASTARS
- `lineModulation`: Rough charcoal-like line work.
- `shading`: Textured shading, atmospheric lighting.
- `anatomy`: Stylized human features with distinct nose structure (animalistic influence).
- `colorPalette`: Dark, moody, theatrical.
- `vibe`: Psychological drama vibe, raw.
- `negative`: Clean digital lines, flat lighting

### 21. 森薰｜乙嫁语
- `lineModulation`: Clean precise fine ink lines.
- `shading`: Obsessive attention to textile patterns and embroidery details.
- `anatomy`: Realistic and gentle facial features.
- `colorPalette`: Historical, rich, detailed.
- `vibe`: Historical slice-of-life aesthetic, high detail, calm.
- `negative`: Messy, empty, modern, sci-fi

### 22. 东村明子｜海月姬
- `lineModulation`: Fluid energetic brush-pen ink lines.
- `shading`: Fast speed lines, trendy.
- `anatomy`: Expressive stylish face.
- `colorPalette`: Trendy modern fashion, Josei manga aesthetic.
- `vibe`: Fast, energetic, stylish, funny.
- `negative`: Stiff, heavy, dark, serious
