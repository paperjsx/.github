# PaperJSX                                                                                                        
                                                                                                
Generate native `.pptx`, `.docx`, `.xlsx`, and `.pdf` files from JSON. No headless Chromium, no HTML conversion — 
real OOXML and real PDF, straight to a buffer.                                                                    
                                                                                                                  
Deterministic output, flexbox layout, and strict Zod validation at every edge. Works in any Node.js `>=18` runtime
 — serverless, edge, CI, desktop.                                                                                 
                                                                                                                  
## Packages                                                     

### Free (Apache-2.0)

- [`@paperjsx/json-to-pptx`](https://www.npmjs.com/package/@paperjsx/json-to-pptx) — PowerPoint from JSON.        
Editable charts, 40+ shapes, diagrams, flex layout.
- [`@paperjsx/json-to-docx`](https://www.npmjs.com/package/@paperjsx/json-to-docx) — Word from JSON. Tables with  
spans, nested lists, images, template hydration (`{{placeholder}}`).                                              
- [`@paperjsx/json-to-pdf`](https://www.npmjs.com/package/@paperjsx/json-to-pdf) — PDF from JSON. Font subsetting,
 tagged structure for accessibility, streaming output.                                                            
- [`@paperjsx/json-to-xlsx`](https://www.npmjs.com/package/@paperjsx/json-to-xlsx) — Excel from JSON. 40+ formula
builders, conditional formatting, style dedup.                                                                    
- [`@paperjsx/templates`](https://www.npmjs.com/package/@paperjsx/templates) — 13 typed templates (invoice, lab
report, pitch deck, …) with Zod schemas and sample data.                                                          
- [`@paperjsx/document-diff`](https://www.npmjs.com/package/@paperjsx/document-diff) — plugin-driven JSON diffing
for review UIs and audit logs.                                                                                    
                                                                
### Commercial                                                                                                    
                                                                
- [`@paperjsx/json-to-pptx-pro`](https://www.npmjs.com/package/@paperjsx/json-to-pptx-pro) — 140+ shapes, 15 chart
 types, `.potx` templates, HarfBuzz shaping, canvas previews. Production / self-hosting license.
- `@paperjsx/json-to-docx-pro` · `@paperjsx/json-to-pdf-pro` · `@paperjsx/json-to-xlsx-pro` — commercial tiers of 
the document engines.                                                                                             
 
### Agents                                                                                                        
                                                                
- [`@paperjsx/mcp-server`](https://www.npmjs.com/package/@paperjsx/mcp-server) — Model Context Protocol server. 13
 tools that let Claude, Cursor, Copilot, Windsurf, Cline, and Gemini actually produce documents, not just describe
 them.                                                                                                            
                                                                
## Quick start

```bash
npm install @paperjsx/json-to-pptx

import { PaperEngine } from "@paperjsx/json-to-pptx";                                                             
import { writeFileSync } from "node:fs";
                                                                                                                  
const buffer = await PaperEngine.render({                       
  type: "Document",                                                                                               
  slides: [{                                                                                                      
    type: "Slide",
    children: [{ type: "Text", content: "Hello, PaperJSX" }],                                                     
  }],                                                                                                             
});
                                                                                                                  
writeFileSync("hello.pptx", buffer);  
```

[Docs](https://paperjsx.com/docs) · [playground](https://paperjsx.com/playground) · [npm](https://paperjsx.com/pricing) · [npm](https://www.npmjs.com/org/paperjsx)

Built by [theplainworks](https://theplainworks.com)
