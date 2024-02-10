---
aliases: 
title: '04 Archives'
tags:
  - meta
created: 2024-02-10T02:51:11.454Z
---

# (relative = false) => {
      const parent = this.config.target_file.parent;
      let folder;
      if (relative) {
        folder = parent.path;
      } else {
        folder = parent.name;
      }
      return folder;
    }