



# Prompt Engineering Cheatsheet 📝

## Anatomy of a Prompt

```mermaid
graph LR
    A[Complete Prompt] --> B[Goal/Task]
    A --> C[Return Format]
    A --> D[Constraints/Warnings]
    A --> E[Context]
    
    style A fill:#3498db,stroke:#2980b9,color:white,stroke-width:2px
    style B fill:#2ecc71,stroke:#27ae60,color:white,stroke-width:2px
    style C fill:#4a69bd,stroke:#3c6382,color:white,stroke-width:2px
    style D fill:#e74c3c,stroke:#c0392b,color:white,stroke-width:2px
    style E fill:#95a5a6,stroke:#7f8c8d,color:white,stroke-width:2px
```

| Component | Purpose | Example |
|-----------|---------|---------|
| **🎯 Goal/Task** | Define what you want | "List 3 medium-length hikes near SF with unique views" |
| **📋 Return Format** | Specify output structure | "For each: name, location, distance, time, features" |
| **⚠️ Warnings** | Prevent errors | "Verify trail names and ensure they're currently open" |
| **🌐 Context** | Add background info | "I'm an intermediate hiker who prefers less crowded trails" |

# Example
> Source: @benhylak on x

![Prompt Anatomy](https://private-user-images.githubusercontent.com/364566/422828647-5ab9d4ca-db9b-4ad3-a5b4-c172b7f10a4f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDE5NjI1NTUsIm5iZiI6MTc0MTk2MjI1NSwicGF0aCI6Ii8zNjQ1NjYvNDIyODI4NjQ3LTVhYjlkNGNhLWRiOWItNGFkMy1hNWI0LWMxNzJiN2YxMGE0Zi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzE0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxNFQxNDI0MTVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02ZGU5ODY4ZmJiMmM5ZWM2MmI3NDA0MmI5YjBlMWEwODEzYWQ4MWUwYjcxYzdiZDQ5Y2M5NjIwOTUzYTQxZmYxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.cOlcKD7NFLuOeMfHwVkh4KTAz2EN7TE-FEzlbvLP2mU)




## Prompting Strategies

```mermaid
graph TD
    A[Prompting Strategies] --> B[Zero-Shot]
    A --> C[Few-Shot]
    A --> D[Chain of Thought]
    
    style A fill:#3498db,stroke:#2980b9,color:white,stroke-width:2px
    style B fill:#e74c3c,stroke:#c0392b,color:white,stroke-width:2px
    style C fill:#2ecc71,stroke:#27ae60,color:white,stroke-width:2px
    style D fill:#9b59b6,stroke:#8e44ad,color:white,stroke-width:2px
```

### Zero-Shot vs. Few-Shot

| Zero-Shot | Few-Shot |
|-----------|----------|
| No examples provided | Provides examples first |
| "Recommend a hiking trail near SF with ocean views" | "Criteria: Family trail, Marin County<br>Answer: Muir Woods...<br><br>Criteria: Dog-friendly, waterfalls<br>Answer: Alamere Falls...<br><br>Criteria: Panoramic views, transit access<br>Answer: ?" |
| Simple but less specific | More verbose but better pattern matching |

### Chain of Thought (CoT)

| Type | Description | Example |
|------|-------------|---------|
| **Zero-Shot CoT** | Add "Let's think step by step" | "What's the best hiking trail for seeing wildflowers in April? Let's think step by step." |
| **Few-Shot CoT** | Show reasoning process examples | "Question: Best dog-friendly trail?<br>Reasoning: 1) Check dog policies 2) Find appropriate length...<br>Answer: Waterfall Loop Trail" |

## Basic vs. Optimized Prompts

```mermaid
graph TD
    subgraph Bad[Bad Prompt]
    BP["Find hiking trails"]
    end
    
    subgraph Good[Good Prompt]
    GP1["GOAL: Recommend 3 moderate trails(4-8 miles)"]
    GP2["near Oakland with views<br>Include: difficulty, location, features"]
    GP3["For context:<br>Im Training for backpacking<br>heres my last runs<br>run 1, from foo to bar. did xyz.<br>run 2, from foo to baz. did xyz."]
    GP1 --> GP2 --> GP3
    end
    
    Bad --> Good
    
    style Bad fill:#990000,stroke:#660000,color:white,stroke-width:2px
    style Good fill:#006600,stroke:#004400,color:white,stroke-width:2px
    style BP fill:#990000,stroke:#660000,color:white
    style GP1 fill:#006600,stroke:#004400,color:white,font-weight:bold
    style GP2 fill:#006600,stroke:#004400,color:white
    style GP3 fill:#006600,stroke:#004400,color:white
```

## Optimization Tips

- ✅ **Be specific**: Clear criteria, measurable targets
- ✅ **Structure output**: Define format, use bullet points
- ✅ **Chunk information**: Organize in clear sections
- ✅ **Add context**: Include relevant preferences/background
- ✅ **Use patterns**: Test cases, expert perspectives, step-by-step format
- ❌ **Avoid**: Being vague, contradictory requirements, ignoring model limitations

_Remember: Great prompts evolve through iteration!_ 
