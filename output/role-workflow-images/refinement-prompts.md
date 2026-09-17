# 图片校对与修订提示词

生成方式：内置 image_gen 图像编辑；参考首轮对应角色图片。

## BA

```text
Edit the provided BA workflow infographic, keeping ALL existing Chinese text, the four-stage layout, 12 nodes, colors, title, and slide index intact. This is the edit target, not just a style reference. Make these precise corrections:
1. Replace EVERY transparent or black-looking background area with a completely opaque pure white canvas (#FFFFFF), including behind the title, all gutters, the footer, and outer margins. No transparent pixels anywhere. Output an ordinary opaque slide image with a solid white page.
2. Add the missing solid blue forward arrow from box 04 “生成澄清问题” DOWN to box 05 “BA／产品确认”. Place the forward arrow slightly left of the existing orange dashed upward return arrow so BOTH directions are distinct.
3. Preserve the orange feedback arrows and all main flows. Attach the long “规则有缺口” feedback clearly from node 10 back to the clarification stage 02.
4. Keep Chinese characters perfectly crisp, no glitches. Make small type and footer readable. 16:9 landscape. Preserve the whole image content without cropping. Do not remove the white background during export. The final image must visually be one clean white PowerPoint slide.
```

## DEV

```text
Edit the provided DEV workflow infographic, keeping its solid white background, four-stage layout, all 12 nodes, title, colors, slide index and existing text intact except the explicitly corrected text.
1. In box 04 “运行修改前检查”, replace the first supporting line with EXACTLY “相关测试、构建与启动检查”. It currently incorrectly says “相关代码”. The second line remains “记录已有失败和环境问题”.
2. Add the missing solid blue downward arrow from box 10 “确认符合方案” to box 11 “完成任务与约定验证”. It must be obvious that the forward flow continues after developer review.
3. Add a clear solid blue forward connector from box 09 “运行检查并看 diff” to box 10 “确认符合方案”, labeled “通过”. Route it in the gutter between columns 3 and 4, with no overlap on text or orange return arrows. Existing orange dashed return arrows must remain pointing backward into node 08. Rearrange that gutter minimally if needed for legibility.
4. All text must be sharply readable and not clipped. No invented characters. Pure opaque WHITE canvas, including title and gutters and footer; NO transparent pixels. Keep 16:9 landscape, no cropping. Final image should be one flat clean white PowerPoint slide.
```

## TEST

```text
Edit the provided TEST workflow infographic, keeping the four-stage layout, all 12 nodes, the Chinese text within nodes, palette, title and slide index intact. This is the edit target.
1. Replace EVERY transparent or black-looking background area with a completely opaque pure WHITE canvas (#FFFFFF): behind title, between lanes, footer, outer margins. No transparent pixels anywhere. Use a solid white slide canvas, do not remove background on export.
2. Fix false self-loops: remove the dashed orange loop directly ABOVE node 04 “生成并评审 AC”, and remove the dashed orange loop directly ABOVE node 07 “对照 Java／Vue 实现”. Preserve the useful dashed arrow from node 04 BACK to node 02 and label that arrow “AC 需补充” in clear space. Node 07 already states product confirmation in text, so no additional rule-conflict self-loop is needed.
3. Ensure the important final-stage topology remains exactly: node 09→10 “发现异常”; node 09→12 “无异常”; node 10→11 “可修复”; node 11 dashed return→09 “复测与回归”; node 10→12 “未解决／阻塞”. NO forward arrow from 11 to 12.
4. Fix clipping of the rightmost failure-route label. Change that edge label to EXACTLY “未解决／阻塞”, place it in white space where fully visible. Allow a little extra outer right margin by minimally narrowing the fourth panel if required. Nothing may touch or go beyond the right edge.
5. Sharply readable Chinese, cleaner consistent line weights, tidy slide typography. 16:9 landscape, preserve full title and all footer content. Output an opaque white PowerPoint slide image, not a cutout.
```

