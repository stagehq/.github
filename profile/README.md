![image](https://user-images.githubusercontent.com/58360188/230451696-23fac203-cd8e-4df9-a643-f0c98e644857.png)

# Stage, API-based developer portfolio
Stage is an API-based developer portfolio platform that helps developers showcase their projects, skills, and experience to potential employers. With an ever-growing collection of building blocks, developers can personalize their portfolios to stand out from the crowd.

Where to contribute:
- [Main Application](https://github.com/stagehq/backstage) to add functionality in editor
- [UI Kit](https://github.com/stagehq/ui) to improve the blocks
 
## Demos
Our Community is already using Stage as their personal Sites:

## Motivation
Developers need to showcase their work and skills in a way that's easy to understand and visually appealing to potential employers. However, building a portfolio website from scratch can be time-consuming and detract from the actual work that developers want to showcase. GetStage aims to simplify this process by providing an API-based platform that connects to various sources of content and social media to create a beautiful and always up-to-date site.

## Features
### Connect your content ✍️: 
With just one click, you can connect your content to Stage. Our powerful block API allows you to extend your content even further.

![image](https://user-images.githubusercontent.com/58360188/230448279-83ad9919-f129-4a21-816d-c5de1c966a03.png)


### Build your own content blocks 🧩: 
You can build your own blocks and publish them to the community.

```typescript
import { Block, List } from "@stagehq/ui";
import * as API from "@stagehq/api";
import { useEffect, useState } from "react";

export default function Extension() {
  const [data, setData] = useState([]);
  
  useEffect(() => {
    const fetchData = async () => {
      const response = await API.gh.get("/repos/owner/repo/issues");
      setData(response.data);
    };
    fetchData();
  }, []);

  return (
    <Block
      title="Title"
      imagePath="https://source.unsplash.com/random/400x200"
      size={2}
    >
      <List>
        {data.map((item) => (
          <List.Item key={item.id} title={item.title} />
        ))}
      </List>
    </Block>
  );
};
```


### Analyze your growth 🌱 (soon): 
Get a clear picture of your growth with detailed analytics. Understand your audience and make better decisions. (Not in place, yet)
