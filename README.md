# Fashionbot

# STYLEGENIE AI
## Agentic GenAI-Powered Personalized Fashion Stylist

**Tagline:** Your Style. Your Identity. Your AI Stylist.

### 1. PROJECT OVERVIEW AND VISION

Build a complete, functional, intelligent fashion recommendation platform called **StyleGenie AI**.

StyleGenie AI is an Agentic AI-powered personal fashion stylist designed for both men and women.

The platform should behave like an actual personal fashion consultant. It should understand the user's fashion identity, analyze their preferences, remember their previous interactions, retrieve relevant fashion knowledge, coordinate outfits, evaluate budgets, analyze wardrobe images and generate visual outfit inspirations.

The central objective is to create a personalized fashion intelligence system that does not simply respond to user queries but understands the user's needs, independently determines the appropriate actions, uses specialized AI agents and tools, evaluates recommendations and delivers a refined final result.

This must be a genuine Agentic GenAI application using:

- Large Language Models (LLMs)
- Multi-Agent AI architecture
- Retrieval-Augmented Generation (RAG)
- Vector embeddings and semantic search
- Persistent user memory
- Multimodal AI
- AI image generation
- Tool calling and agent orchestration
- Feedback-driven personalization

Do not create a simple chatbot with hardcoded responses or merely simulated agents.

---

# 2. TECHNOLOGY STACK

Use the following technology architecture:

**Frontend**
- React.js
- TypeScript
- Tailwind CSS
- Modern reusable UI components
- Responsive design

**Backend**
- Supabase
- PostgreSQL
- Supabase Edge Functions
- Supabase Authentication
- Supabase Storage

**Generative AI**
- Google Gemini API for LLM reasoning.
- Gemini-supported embedding model for semantic search.
- Compatible multimodal model for image understanding.
- Supported image-generation model for outfit visualization.

**RAG**
- Supabase pgvector.
- Vector embeddings.
- Semantic similarity search.
- Document chunking and metadata filtering.

**Agent Orchestration**
- Implement a genuine server-side agent orchestrator using Gemini tool/function calling and controlled execution workflows.
- Use specialized agents with clearly defined responsibilities.
- Maintain structured inputs, outputs and execution states.

All API keys must be stored securely in environment variables or server-side secrets. Never expose API credentials in frontend code.

Verify model availability and API compatibility before implementation. Do not assume an image-generation or embedding model is available without checking.

---

# 3. MULTI-AGENT AI ARCHITECTURE

This is the most important component of the project.

Create a multi-agent fashion intelligence architecture where a central orchestrator understands user requests and coordinates specialized agents.

## Agent 1: Master Orchestrator Agent

Role: Central decision-making agent.

Responsibilities:
- Understand incoming user queries.
- Identify user intent.
- Retrieve the user's fashion identity.
- Determine which specialist agents are required.
- Delegate tasks to appropriate agents.
- Coordinate agent outputs.
- Handle dependencies between agents.
- Validate the final result.
- Return a unified response.

The orchestrator must dynamically decide which agents to invoke rather than invoking every agent for every query.

Example:

User: "I need an elegant college farewell outfit under ₹1500."

The orchestrator should:
1. Understand the occasion and budget.
2. Retrieve the user's personal fashion preferences.
3. Call the fashion knowledge retrieval agent.
4. Call the outfit recommendation agent.
5. Call the budget validation agent.
6. Call the visual styling agent if the user requests images.
7. Combine the results.
8. Return personalized recommendations.

## Agent 2: Personalization Agent

Role: Understand and maintain the user's fashion identity.

Responsibilities:
- Read user profile information.
- Retrieve persistent fashion preferences.
- Analyze previous interactions.
- Identify preferred aesthetics.
- Identify disliked styles and colors.
- Update approved preferences.
- Adapt future recommendations.

Maintain:
- Preferred fashion categories.
- Preferred aesthetics.
- Preferred colors.
- Colors to avoid.
- Preferred clothing fits.
- Budget preferences.
- Favorite outfit types.
- Feedback history.
- User-approved long-term memories.

The agent must distinguish temporary requests from permanent preferences.

## Agent 3: Fashion Knowledge Retrieval Agent

Role: Retrieve relevant fashion knowledge using RAG.

Responsibilities:
- Understand the fashion-related query.
- Generate query embeddings.
- Search the vector database.
- Retrieve relevant fashion knowledge chunks.
- Apply metadata filters.
- Rank relevant information.
- Provide source references.
- Supply grounded context to other agents.

The knowledge base should contain:
- Color theory.
- Color coordination.
- Men's fashion.
- Women's fashion.
- Unisex fashion.
- Garment combinations.
- Clothing fit and silhouettes.
- Fabric knowledge.
- Seasonal styling.
- Occasion-based styling.
- Accessories.
- Traditional and contemporary fashion.

Do not fabricate retrieved sources. If no relevant information exists, clearly indicate that retrieval did not return relevant material.

## Agent 4: Outfit Recommendation Agent

Role: Generate personalized outfit combinations.

Responsibilities:
- Understand the occasion.
- Consider the user's preferences.
- Consider retrieved fashion knowledge.
- Consider available wardrobe items.
- Respect the budget.
- Generate distinct outfit combinations.
- Explain why each outfit works.

Each outfit must include:
- Outfit name.
- Styling concept.
- Topwear.
- Bottomwear.
- Footwear.
- Accessories.
- Color palette.
- Estimated individual prices.
- Total estimated cost.
- Styling explanation.
- Personalization explanation.
- Alternative combinations.

Generate three distinct recommendations whenever appropriate.

Avoid repetitive recommendations.

## Agent 5: Budget Intelligence Agent

Role: Evaluate financial feasibility.

Responsibilities:
- Calculate item-wise outfit costs.
- Validate the total budget.
- Suggest affordable alternatives.
- Identify budget overruns.
- Prioritize essential clothing items.
- Optimize outfit combinations within the user's budget.

All prices must be identified as estimates unless verified against actual product data.

The agent must perform actual arithmetic validation rather than simply trusting the LLM-generated total.

## Agent 6: Color and Style Coordination Agent

Role: Analyze visual compatibility and styling.

Responsibilities:
- Coordinate colors.
- Suggest complementary combinations.
- Identify suitable contrasts.
- Recommend accessories.
- Suggest appropriate clothing silhouettes.
- Recommend combinations based on the user's chosen aesthetic.

Provide visual color palettes and HEX codes.

## Agent 7: Wardrobe Vision Agent

Role: Multimodal fashion understanding.

Responsibilities:
- Accept uploaded clothing images.
- Analyze visible garments.
- Identify clothing categories.
- Identify visible colors and patterns.
- Identify possible outfit combinations.
- Recommend complementary items.
- Help users create outfits using existing wardrobe items.

Allow users to save analyzed clothing items in their virtual wardrobe.

Do not infer sensitive personal characteristics from photographs.

## Agent 8: Visual Generation Agent

Role: Generate fashion inspiration.

Responsibilities:
- Convert outfit recommendations into detailed image prompts.
- Generate visual outfit inspiration using the configured image model.
- Maintain consistency with the selected fashion aesthetic.
- Generate multiple visual variations when requested.
- Save generated images.
- Associate images with their respective outfit recommendations.

Never pretend that a generated image was successfully created if the image API fails.

## Agent 9: Feedback and Learning Agent

Role: Improve recommendations over time.

Responsibilities:
- Process user likes and dislikes.
- Record saved outfits.
- Identify frequently preferred styles.
- Learn from rejected recommendations.
- Update personalization signals.
- Improve subsequent outfit recommendations.

Never permanently change a user preference based on a single ambiguous interaction.

---

# 4. AGENTIC WORKFLOW

Implement an actual orchestrated workflow.

The system should work as follows:

USER QUERY
↓
MASTER ORCHESTRATOR
↓
INTENT AND CONTEXT UNDERSTANDING
↓
PERSONALIZATION AGENT
↓
RAG KNOWLEDGE RETRIEVAL AGENT
↓
OUTFIT RECOMMENDATION AGENT
↓
BUDGET VALIDATION AGENT
↓
COLOR COORDINATION AGENT
↓
VISUAL GENERATION AGENT (when requested)
↓
FINAL VALIDATION
↓
PERSONALIZED USER RESPONSE

The orchestrator should select only the relevant agents for each request.

For example:
- A color matching question does not require the budget agent.
- A wardrobe image question requires the vision agent.
- A complete occasion-based outfit request can require personalization, retrieval, outfit planning, budget and color agents.
- A request for outfit images invokes the visual generation agent.

Implement structured agent inputs and outputs.

Include:
- Execution status.
- Agent name.
- Agent task.
- Input context.
- Output.
- Error state.
- Execution order.

Provide an attractive, user-friendly agent activity indicator in the interface. Do not expose private chain-of-thought reasoning. Display concise activity summaries such as "Understanding your style", "Retrieving fashion knowledge" and "Checking your budget".

If an agent fails, provide a controlled fallback rather than crashing the entire application.

The agents must actually perform their assigned operations. Do not create nine visually displayed agents that all return the same generic LLM response.

---

# 5. ADVANCED RAG IMPLEMENTATION

Implement a real RAG pipeline.

### Knowledge ingestion

Create an administrator-accessible fashion knowledge management interface.

Allow authorized administrators to upload:
- PDF documents.
- Text files.
- Fashion guides.
- Curated styling references.

Process documents through:
1. Text extraction.
2. Cleaning.
3. Chunking.
4. Metadata extraction.
5. Embedding generation.
6. Vector storage.

### Vector database

Use Supabase PostgreSQL with pgvector.

Store:
- Document ID.
- Chunk ID.
- Text content.
- Embedding.
- Source title.
- Category.
- Occasion.
- Fashion type.
- Metadata.

### Retrieval process

For each relevant user query:
1. Create query embedding.
2. Perform semantic vector search.
3. Apply metadata filters.
4. Retrieve the most relevant chunks.
5. Rank results.
6. Supply retrieved context to the appropriate agent.
7. Generate a grounded response through Gemini.

Implement a configurable top-k retrieval parameter and similarity threshold.

Include source references in relevant recommendations when available.

Seed the knowledge base with curated sample fashion knowledge so that RAG can be demonstrated immediately.

The knowledge base must be separate from the user's personal memory.

---

# 6. PERSONALIZATION AND MEMORY

Create a persistent fashion identity system.

### Initial onboarding

Ask users about:

- Fashion category: Men, Women or Unisex.
- Preferred aesthetics.
- Preferred colors.
- Colors they dislike.
- Preferred clothing fits.
- Clothing preferences.
- Preferred occasions.
- Budget range.
- Favorite styles.
- Optional clothing sizes.
- Optional wardrobe uploads.

Fashion aesthetics:
Minimalist, Old Money, Streetwear, Elegant, Classic, Casual, Formal, Traditional, Vintage, Luxury, Bohemian, Smart Casual and Trendy.

### Memory architecture

Implement:

**Short-term memory**
Current conversation and recent messages.

**Long-term memory**
Approved fashion preferences stored in Supabase.

**Contextual memory**
Relevant previous interactions retrieved when needed.

**Feedback memory**
Likes, dislikes, saved outfits and rejected recommendations.

Create a My Fashion Identity page where users can:
- View their style profile.
- Edit preferences.
- Review saved memories.
- Delete memories.
- Reset personalization.

The chatbot should adapt its recommendations automatically based on the available profile context.

---

# 7. MAIN APPLICATION FEATURES

## A. AI Fashion Chat

Create a sophisticated conversational experience.

Users should be able to ask:
- What should I wear for a college farewell?
- Suggest a minimal outfit under ₹1500.
- How can I style an oversized shirt?
- What goes well with beige trousers?
- Suggest a wedding outfit for men.
- Create an elegant date-night look.
- Help me style clothes from my wardrobe.

Include:
- Conversation history.
- New chat.
- Suggested prompts.
- File and image upload.
- Follow-up questions.
- Agent activity indicator.
- Outfit recommendation cards.
- Save and regenerate actions.

## B. Personalized Outfit Generator

Provide filters for:
- Fashion category.
- Occasion.
- Budget.
- Style aesthetic.
- Colors.
- Weather.
- Wardrobe items.
- Custom instructions.

Generate three distinct outfits with complete descriptions and estimated budgets.

## C. AI Visual Outfit Studio

Generate visual representations of the outfit recommendations.

Include:
- Image generation.
- Regeneration.
- Multiple variations.
- Image gallery.
- Save to lookbook.
- Outfit-to-image association.

## D. My Virtual Wardrobe

Allow users to upload clothing images and categorize garments.

Categories:
- Tops.
- Shirts.
- T-shirts.
- Bottoms.
- Dresses.
- Ethnic wear.
- Outerwear.
- Footwear.
- Accessories.

Use the Wardrobe Vision Agent to analyze clothing and suggest combinations.

## E. Smart Color Studio

Provide:
- Color matching.
- Complementary colors.
- Contrast combinations.
- Neutral palettes.
- Accessory coordination.
- HEX color palettes.

## F. Occasion Stylist

Support:
- College.
- Office.
- Interview.
- Wedding.
- Reception.
- Party.
- Date.
- Travel.
- Vacation.
- Casual.
- Festival.
- Custom occasions.

## G. My Lookbook

Allow users to save:
- Outfit recommendations.
- Generated images.
- Styling notes.
- Favorite combinations.

Provide filtering by date, occasion and fashion aesthetic.

## H. Fashion Identity Dashboard

Show:
- Personal style profile.
- Preferred fashion aesthetic.
- Color palette.
- Recent outfits.
- Saved looks.
- Recommendation history.
- Fashion inspiration.

---

# 8. UI/UX AND DESIGN DIRECTION

The interface must be exceptionally polished and visually engaging.

Design the application like a premium fashion-tech startup.

### Brand identity

STYLEGENIE AI

Tagline:
"Your Style. Your Identity. Your AI Stylist."

### Color palette

- Warm ivory: #F8F5F0
- Soft cream: #EEE7DD
- Deep charcoal: #242321
- Muted plum: #67445F
- Lavender accent: #B6A2C8
- Warm taupe: #A58E7B

Use these colors consistently, with sufficient contrast.

### Typography

Use elegant editorial serif typography for major headings and modern sans-serif typography for body text.

### Layout

Create:
- Beautiful landing page.
- Premium onboarding experience.
- Personalized dashboard.
- Elegant AI chat layout.
- Outfit recommendation cards.
- Visual image gallery.
- Interactive wardrobe.
- Fashion profile settings.

### Navigation

Use a refined sidebar on desktop and responsive navigation on mobile.

Navigation:
1. Home.
2. AI Stylist.
3. Outfit Generator.
4. My Wardrobe.
5. Color Studio.
6. My Lookbook.
7. Fashion Identity.
8. Settings.

### User experience

Include:
- Smooth animations.
- Elegant transitions.
- Loading skeletons.
- Typing indicators.
- Toast notifications.
- Empty states.
- Error handling.
- Responsive cards.
- Attractive image layouts.
- Accessible controls.

Avoid clutter, excessive gradients and generic dashboard designs.

---

# 9. DATABASE DESIGN

Create a normalized and secure Supabase database.

Tables:

1. user_profiles
2. fashion_preferences
3. user_memories
4. chat_sessions
5. chat_messages
6. fashion_documents
7. fashion_document_chunks
8. fashion_embeddings
9. wardrobe_items
10. outfit_recommendations
11. generated_outfit_images
12. saved_outfits
13. recommendation_feedback
14. agent_execution_logs

Use suitable relationships, indexes, timestamps and constraints.

Implement Row Level Security for all user-owned records.

Users must only access their own private data.

Agent execution logs must not expose API keys, private prompts or sensitive user data.

Use secure server-side functions for all AI operations.

---

# 10. FUNCTIONAL REQUIREMENTS

The following are mandatory:

- Authentication must work.
- Onboarding must save actual preferences.
- Chatbot must use the Gemini API.
- Agents must perform genuine specialized operations.
- Orchestrator must coordinate agents.
- RAG must retrieve real knowledge from pgvector.
- Retrieved knowledge must be passed to Gemini.
- Persistent user memory must work.
- Conversation history must persist.
- Wardrobe image analysis must work when configured.
- Outfit recommendations must be personalized.
- Budget calculations must be validated.
- Image generation must work when configured.
- Saved looks must persist.
- Feedback must influence subsequent recommendations.
- Database access must be protected.
- All major pages must work on desktop and mobile.

Never substitute fake AI responses for actual integrations.

If API credentials are unavailable, build the integration points, configuration instructions and clear setup states. Do not falsely label an unconfigured feature as operational.

---

# 11. DEVELOPMENT PRIORITIES

Implement in this order to ensure the project can be completed efficiently.

PHASE 1:
Brand identity, design system, landing page, navigation and dashboard.

PHASE 2:
Authentication and personalized onboarding.

PHASE 3:
Gemini integration and working fashion chatbot.

PHASE 4:
Master orchestrator and specialist agent workflow.

PHASE 5:
User memory and personalization.

PHASE 6:
RAG pipeline, document ingestion, embeddings and pgvector retrieval.

PHASE 7:
Outfit generation, color coordination and budget validation.

PHASE 8:
Wardrobe image analysis and visual outfit generation.

PHASE 9:
Lookbook, feedback, security and final testing.

Prioritize a working end-to-end core experience before implementing optional enhancements.

---

# 12. FINAL ACCEPTANCE CRITERIA

The final project must demonstrate the following real workflow:

A user logs in and completes their fashion personality assessment.

The platform creates and saves a personalized fashion identity.

The user asks:
"Suggest a minimal college farewell outfit under ₹1500."

The Master Orchestrator understands the query.

The Personalization Agent retrieves the user's saved preferences.

The Knowledge Retrieval Agent searches the fashion knowledge base through RAG.

The Outfit Recommendation Agent creates suitable outfit combinations.

The Budget Intelligence Agent validates the prices.

The Color Coordination Agent checks the combinations.

The Visual Generation Agent creates an outfit image when requested.

The orchestrator combines the results and returns personalized recommendations.

The user likes and saves an outfit.

The Feedback Agent records that preference.

In a later conversation, the application uses the saved preference to produce better recommendations.

This complete workflow must be demonstrated during the final presentation.

### FINAL EXPECTATION

Deliver a premium, fully functional, agentic GenAI fashion platform.

It should demonstrate:
- Genuine agent orchestration.
- RAG-based fashion knowledge retrieval.
- LLM-powered reasoning.
- Personalized long-term memory.
- Multimodal fashion intelligence.
- AI image generation.
- Secure persistent data.
- An engaging and polished interface.

The finished product must look like a real fashion technology startup and function like an intelligent personal fashion consultant.

Do not stop at generating a landing page, static UI or simulated chatbot.

Build the actual application, connect the backend, implement the AI workflows and test the end-to-end experience.

**PROJECT NAME: STYLEGENIE AI**
**PROJECT CATEGORY: AGENTIC GENERATIVE AI**
**TARGET USERS: MEN AND WOMEN**
**CORE TECHNOLOGIES: MULTI-AGENT AI + RAG + LLM + MEMORY + MULTIMODAL AI**
**CURRENCY: INR (₹)**

# STYLEGENIE AI
## Agentic GenAI-Powered Personalized Fashion Stylist

**Tagline:** Your Style. Your Identity. Your AI Stylist.

### 1. PROJECT OVERVIEW AND VISION

Build a complete, functional, intelligent fashion recommendation platform called **StyleGenie AI**.

StyleGenie AI is an Agentic AI-powered personal fashion stylist designed for both men and women.

The platform should behave like an actual personal fashion consultant. It should understand the user's fashion identity, analyze their preferences, remember their previous interactions, retrieve relevant fashion knowledge, coordinate outfits, evaluate budgets, analyze wardrobe images and generate visual outfit inspirations.

The central objective is to create a personalized fashion intelligence system that does not simply respond to user queries but understands the user's needs, independently determines the appropriate actions, uses specialized AI agents and tools, evaluates recommendations and delivers a refined final result.

This must be a genuine Agentic GenAI application using:

- Large Language Models (LLMs)
- Multi-Agent AI architecture
- Retrieval-Augmented Generation (RAG)
- Vector embeddings and semantic search
- Persistent user memory
- Multimodal AI
- AI image generation
- Tool calling and agent orchestration
- Feedback-driven personalization

Do not create a simple chatbot with hardcoded responses or merely simulated agents.

---

# 2. TECHNOLOGY STACK

Use the following technology architecture:

**Frontend**
- React.js
- TypeScript
- Tailwind CSS
- Modern reusable UI components
- Responsive design

**Backend**
- Supabase
- PostgreSQL
- Supabase Edge Functions
- Supabase Authentication
- Supabase Storage

**Generative AI**
- Google Gemini API for LLM reasoning.
- Gemini-supported embedding model for semantic search.
- Compatible multimodal model for image understanding.
- Supported image-generation model for outfit visualization.

**RAG**
- Supabase pgvector.
- Vector embeddings.
- Semantic similarity search.
- Document chunking and metadata filtering.

**Agent Orchestration**
- Implement a genuine server-side agent orchestrator using Gemini tool/function calling and controlled execution workflows.
- Use specialized agents with clearly defined responsibilities.
- Maintain structured inputs, outputs and execution states.

All API keys must be stored securely in environment variables or server-side secrets. Never expose API credentials in frontend code.

Verify model availability and API compatibility before implementation. Do not assume an image-generation or embedding model is available without checking.

---

# 3. MULTI-AGENT AI ARCHITECTURE

This is the most important component of the project.

Create a multi-agent fashion intelligence architecture where a central orchestrator understands user requests and coordinates specialized agents.

## Agent 1: Master Orchestrator Agent

Role: Central decision-making agent.

Responsibilities:
- Understand incoming user queries.
- Identify user intent.
- Retrieve the user's fashion identity.
- Determine which specialist agents are required.
- Delegate tasks to appropriate agents.
- Coordinate agent outputs.
- Handle dependencies between agents.
- Validate the final result.
- Return a unified response.

The orchestrator must dynamically decide which agents to invoke rather than invoking every agent for every query.

Example:

User: "I need an elegant college farewell outfit under ₹1500."

The orchestrator should:
1. Understand the occasion and budget.
2. Retrieve the user's personal fashion preferences.
3. Call the fashion knowledge retrieval agent.
4. Call the outfit recommendation agent.
5. Call the budget validation agent.
6. Call the visual styling agent if the user requests images.
7. Combine the results.
8. Return personalized recommendations.

## Agent 2: Personalization Agent

Role: Understand and maintain the user's fashion identity.

Responsibilities:
- Read user profile information.
- Retrieve persistent fashion preferences.
- Analyze previous interactions.
- Identify preferred aesthetics.
- Identify disliked styles and colors.
- Update approved preferences.
- Adapt future recommendations.

Maintain:
- Preferred fashion categories.
- Preferred aesthetics.
- Preferred colors.
- Colors to avoid.
- Preferred clothing fits.
- Budget preferences.
- Favorite outfit types.
- Feedback history.
- User-approved long-term memories.

The agent must distinguish temporary requests from permanent preferences.

## Agent 3: Fashion Knowledge Retrieval Agent

Role: Retrieve relevant fashion knowledge using RAG.

Responsibilities:
- Understand the fashion-related query.
- Generate query embeddings.
- Search the vector database.
- Retrieve relevant fashion knowledge chunks.
- Apply metadata filters.
- Rank relevant information.
- Provide source references.
- Supply grounded context to other agents.

The knowledge base should contain:
- Color theory.
- Color coordination.
- Men's fashion.
- Women's fashion.
- Unisex fashion.
- Garment combinations.
- Clothing fit and silhouettes.
- Fabric knowledge.
- Seasonal styling.
- Occasion-based styling.
- Accessories.
- Traditional and contemporary fashion.

Do not fabricate retrieved sources. If no relevant information exists, clearly indicate that retrieval did not return relevant material.

## Agent 4: Outfit Recommendation Agent

Role: Generate personalized outfit combinations.

Responsibilities:
- Understand the occasion.
- Consider the user's preferences.
- Consider retrieved fashion knowledge.
- Consider available wardrobe items.
- Respect the budget.
- Generate distinct outfit combinations.
- Explain why each outfit works.

Each outfit must include:
- Outfit name.
- Styling concept.
- Topwear.
- Bottomwear.
- Footwear.
- Accessories.
- Color palette.
- Estimated individual prices.
- Total estimated cost.
- Styling explanation.
- Personalization explanation.
- Alternative combinations.

Generate three distinct recommendations whenever appropriate.

Avoid repetitive recommendations.

## Agent 5: Budget Intelligence Agent

Role: Evaluate financial feasibility.

Responsibilities:
- Calculate item-wise outfit costs.
- Validate the total budget.
- Suggest affordable alternatives.
- Identify budget overruns.
- Prioritize essential clothing items.
- Optimize outfit combinations within the user's budget.

All prices must be identified as estimates unless verified against actual product data.

The agent must perform actual arithmetic validation rather than simply trusting the LLM-generated total.

## Agent 6: Color and Style Coordination Agent

Role: Analyze visual compatibility and styling.

Responsibilities:
- Coordinate colors.
- Suggest complementary combinations.
- Identify suitable contrasts.
- Recommend accessories.
- Suggest appropriate clothing silhouettes.
- Recommend combinations based on the user's chosen aesthetic.

Provide visual color palettes and HEX codes.

## Agent 7: Wardrobe Vision Agent

Role: Multimodal fashion understanding.

Responsibilities:
- Accept uploaded clothing images.
- Analyze visible garments.
- Identify clothing categories.
- Identify visible colors and patterns.
- Identify possible outfit combinations.
- Recommend complementary items.
- Help users create outfits using existing wardrobe items.

Allow users to save analyzed clothing items in their virtual wardrobe.

Do not infer sensitive personal characteristics from photographs.

## Agent 8: Visual Generation Agent

Role: Generate fashion inspiration.

Responsibilities:
- Convert outfit recommendations into detailed image prompts.
- Generate visual outfit inspiration using the configured image model.
- Maintain consistency with the selected fashion aesthetic.
- Generate multiple visual variations when requested.
- Save generated images.
- Associate images with their respective outfit recommendations.

Never pretend that a generated image was successfully created if the image API fails.

## Agent 9: Feedback and Learning Agent

Role: Improve recommendations over time.

Responsibilities:
- Process user likes and dislikes.
- Record saved outfits.
- Identify frequently preferred styles.
- Learn from rejected recommendations.
- Update personalization signals.
- Improve subsequent outfit recommendations.

Never permanently change a user preference based on a single ambiguous interaction.

---

# 4. AGENTIC WORKFLOW

Implement an actual orchestrated workflow.

The system should work as follows:

USER QUERY
↓
MASTER ORCHESTRATOR
↓
INTENT AND CONTEXT UNDERSTANDING
↓
PERSONALIZATION AGENT
↓
RAG KNOWLEDGE RETRIEVAL AGENT
↓
OUTFIT RECOMMENDATION AGENT
↓
BUDGET VALIDATION AGENT
↓
COLOR COORDINATION AGENT
↓
VISUAL GENERATION AGENT (when requested)
↓
FINAL VALIDATION
↓
PERSONALIZED USER RESPONSE

The orchestrator should select only the relevant agents for each request.

For example:
- A color matching question does not require the budget agent.
- A wardrobe image question requires the vision agent.
- A complete occasion-based outfit request can require personalization, retrieval, outfit planning, budget and color agents.
- A request for outfit images invokes the visual generation agent.

Implement structured agent inputs and outputs.

Include:
- Execution status.
- Agent name.
- Agent task.
- Input context.
- Output.
- Error state.
- Execution order.

Provide an attractive, user-friendly agent activity indicator in the interface. Do not expose private chain-of-thought reasoning. Display concise activity summaries such as "Understanding your style", "Retrieving fashion knowledge" and "Checking your budget".

If an agent fails, provide a controlled fallback rather than crashing the entire application.

The agents must actually perform their assigned operations. Do not create nine visually displayed agents that all return the same generic LLM response.

---

# 5. ADVANCED RAG IMPLEMENTATION

Implement a real RAG pipeline.

### Knowledge ingestion

Create an administrator-accessible fashion knowledge management interface.

Allow authorized administrators to upload:
- PDF documents.
- Text files.
- Fashion guides.
- Curated styling references.

Process documents through:
1. Text extraction.
2. Cleaning.
3. Chunking.
4. Metadata extraction.
5. Embedding generation.
6. Vector storage.

### Vector database

Use Supabase PostgreSQL with pgvector.

Store:
- Document ID.
- Chunk ID.
- Text content.
- Embedding.
- Source title.
- Category.
- Occasion.
- Fashion type.
- Metadata.

### Retrieval process

For each relevant user query:
1. Create query embedding.
2. Perform semantic vector search.
3. Apply metadata filters.
4. Retrieve the most relevant chunks.
5. Rank results.
6. Supply retrieved context to the appropriate agent.
7. Generate a grounded response through Gemini.

Implement a configurable top-k retrieval parameter and similarity threshold.

Include source references in relevant recommendations when available.

Seed the knowledge base with curated sample fashion knowledge so that RAG can be demonstrated immediately.

The knowledge base must be separate from the user's personal memory.

---

# 6. PERSONALIZATION AND MEMORY

Create a persistent fashion identity system.

### Initial onboarding

Ask users about:

- Fashion category: Men, Women or Unisex.
- Preferred aesthetics.
- Preferred colors.
- Colors they dislike.
- Preferred clothing fits.
- Clothing preferences.
- Preferred occasions.
- Budget range.
- Favorite styles.
- Optional clothing sizes.
- Optional wardrobe uploads.

Fashion aesthetics:
Minimalist, Old Money, Streetwear, Elegant, Classic, Casual, Formal, Traditional, Vintage, Luxury, Bohemian, Smart Casual and Trendy.

### Memory architecture

Implement:

**Short-term memory**
Current conversation and recent messages.

**Long-term memory**
Approved fashion preferences stored in Supabase.

**Contextual memory**
Relevant previous interactions retrieved when needed.

**Feedback memory**
Likes, dislikes, saved outfits and rejected recommendations.

Create a My Fashion Identity page where users can:
- View their style profile.
- Edit preferences.
- Review saved memories.
- Delete memories.
- Reset personalization.

The chatbot should adapt its recommendations automatically based on the available profile context.

---

# 7. MAIN APPLICATION FEATURES

## A. AI Fashion Chat

Create a sophisticated conversational experience.

Users should be able to ask:
- What should I wear for a college farewell?
- Suggest a minimal outfit under ₹1500.
- How can I style an oversized shirt?
- What goes well with beige trousers?
- Suggest a wedding outfit for men.
- Create an elegant date-night look.
- Help me style clothes from my wardrobe.

Include:
- Conversation history.
- New chat.
- Suggested prompts.
- File and image upload.
- Follow-up questions.
- Agent activity indicator.
- Outfit recommendation cards.
- Save and regenerate actions.

## B. Personalized Outfit Generator

Provide filters for:
- Fashion category.
- Occasion.
- Budget.
- Style aesthetic.
- Colors.
- Weather.
- Wardrobe items.
- Custom instructions.

Generate three distinct outfits with complete descriptions and estimated budgets.

## C. AI Visual Outfit Studio

Generate visual representations of the outfit recommendations.

Include:
- Image generation.
- Regeneration.
- Multiple variations.
- Image gallery.
- Save to lookbook.
- Outfit-to-image association.

## D. My Virtual Wardrobe

Allow users to upload clothing images and categorize garments.

Categories:
- Tops.
- Shirts.
- T-shirts.
- Bottoms.
- Dresses.
- Ethnic wear.
- Outerwear.
- Footwear.
- Accessories.

Use the Wardrobe Vision Agent to analyze clothing and suggest combinations.

## E. Smart Color Studio

Provide:
- Color matching.
- Complementary colors.
- Contrast combinations.
- Neutral palettes.
- Accessory coordination.
- HEX color palettes.

## F. Occasion Stylist

Support:
- College.
- Office.
- Interview.
- Wedding.
- Reception.
- Party.
- Date.
- Travel.
- Vacation.
- Casual.
- Festival.
- Custom occasions.

## G. My Lookbook

Allow users to save:
- Outfit recommendations.
- Generated images.
- Styling notes.
- Favorite combinations.

Provide filtering by date, occasion and fashion aesthetic.

## H. Fashion Identity Dashboard

Show:
- Personal style profile.
- Preferred fashion aesthetic.
- Color palette.
- Recent outfits.
- Saved looks.
- Recommendation history.
- Fashion inspiration.

---

# 8. UI/UX AND DESIGN DIRECTION

The interface must be exceptionally polished and visually engaging.

Design the application like a premium fashion-tech startup.

### Brand identity

STYLEGENIE AI

Tagline:
"Your Style. Your Identity. Your AI Stylist."

### Color palette

- Warm ivory: #F8F5F0
- Soft cream: #EEE7DD
- Deep charcoal: #242321
- Muted plum: #67445F
- Lavender accent: #B6A2C8
- Warm taupe: #A58E7B

Use these colors consistently, with sufficient contrast.

### Typography

Use elegant editorial serif typography for major headings and modern sans-serif typography for body text.

### Layout

Create:
- Beautiful landing page.
- Premium onboarding experience.
- Personalized dashboard.
- Elegant AI chat layout.
- Outfit recommendation cards.
- Visual image gallery.
- Interactive wardrobe.
- Fashion profile settings.

### Navigation

Use a refined sidebar on desktop and responsive navigation on mobile.

Navigation:
1. Home.
2. AI Stylist.
3. Outfit Generator.
4. My Wardrobe.
5. Color Studio.
6. My Lookbook.
7. Fashion Identity.
8. Settings.

### User experience

Include:
- Smooth animations.
- Elegant transitions.
- Loading skeletons.
- Typing indicators.
- Toast notifications.
- Empty states.
- Error handling.
- Responsive cards.
- Attractive image layouts.
- Accessible controls.

Avoid clutter, excessive gradients and generic dashboard designs.

---

# 9. DATABASE DESIGN

Create a normalized and secure Supabase database.

Tables:

1. user_profiles
2. fashion_preferences
3. user_memories
4. chat_sessions
5. chat_messages
6. fashion_documents
7. fashion_document_chunks
8. fashion_embeddings
9. wardrobe_items
10. outfit_recommendations
11. generated_outfit_images
12. saved_outfits
13. recommendation_feedback
14. agent_execution_logs

Use suitable relationships, indexes, timestamps and constraints.

Implement Row Level Security for all user-owned records.

Users must only access their own private data.

Agent execution logs must not expose API keys, private prompts or sensitive user data.

Use secure server-side functions for all AI operations.

---

# 10. FUNCTIONAL REQUIREMENTS

The following are mandatory:

- Authentication must work.
- Onboarding must save actual preferences.
- Chatbot must use the Gemini API.
- Agents must perform genuine specialized operations.
- Orchestrator must coordinate agents.
- RAG must retrieve real knowledge from pgvector.
- Retrieved knowledge must be passed to Gemini.
- Persistent user memory must work.
- Conversation history must persist.
- Wardrobe image analysis must work when configured.
- Outfit recommendations must be personalized.
- Budget calculations must be validated.
- Image generation must work when configured.
- Saved looks must persist.
- Feedback must influence subsequent recommendations.
- Database access must be protected.
- All major pages must work on desktop and mobile.

Never substitute fake AI responses for actual integrations.

If API credentials are unavailable, build the integration points, configuration instructions and clear setup states. Do not falsely label an unconfigured feature as operational.

---

# 11. DEVELOPMENT PRIORITIES

Implement in this order to ensure the project can be completed efficiently.

PHASE 1:
Brand identity, design system, landing page, navigation and dashboard.

PHASE 2:
Authentication and personalized onboarding.

PHASE 3:
Gemini integration and working fashion chatbot.

PHASE 4:
Master orchestrator and specialist agent workflow.

PHASE 5:
User memory and personalization.

PHASE 6:
RAG pipeline, document ingestion, embeddings and pgvector retrieval.

PHASE 7:
Outfit generation, color coordination and budget validation.

PHASE 8:
Wardrobe image analysis and visual outfit generation.

PHASE 9:
Lookbook, feedback, security and final testing.

Prioritize a working end-to-end core experience before implementing optional enhancements.

---

# 12. FINAL ACCEPTANCE CRITERIA

The final project must demonstrate the following real workflow:

A user logs in and completes their fashion personality assessment.

The platform creates and saves a personalized fashion identity.

The user asks:
"Suggest a minimal college farewell outfit under ₹1500."

The Master Orchestrator understands the query.

The Personalization Agent retrieves the user's saved preferences.

The Knowledge Retrieval Agent searches the fashion knowledge base through RAG.

The Outfit Recommendation Agent creates suitable outfit combinations.

The Budget Intelligence Agent validates the prices.

The Color Coordination Agent checks the combinations.

The Visual Generation Agent creates an outfit image when requested.

The orchestrator combines the results and returns personalized recommendations.

The user likes and saves an outfit.

The Feedback Agent records that preference.

In a later conversation, the application uses the saved preference to produce better recommendations.

This complete workflow must be demonstrated during the final presentation.

### FINAL EXPECTATION

Deliver a premium, fully functional, agentic GenAI fashion platform.

It should demonstrate:
- Genuine agent orchestration.
- RAG-based fashion knowledge retrieval.
- LLM-powered reasoning.
- Personalized long-term memory.
- Multimodal fashion intelligence.
- AI image generation.
- Secure persistent data.
- An engaging and polished interface.

The finished product must look like a real fashion technology startup and function like an intelligent personal fashion consultant.

Do not stop at generating a landing page, static UI or simulated chatbot.

Build the actual application, connect the backend, implement the AI workflows and test the end-to-end experience.

**PROJECT NAME: STYLEGENIE AI**
**PROJECT CATEGORY: AGENTIC GENERATIVE AI**
**TARGET USERS: MEN AND WOMEN**
**CORE TECHNOLOGIES: MULTI-AGENT AI + RAG + LLM + MEMORY + MULTIMODAL AI**
**CURRENCY: INR (₹)**

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/ef75d8f0-7a3a-4b92-8721-9152241b3d5c).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
