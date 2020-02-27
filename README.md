# sr-client-1
Ads for some SR client - theoretical git repo

# Clients
Each client gets its own repo. This repo is a dummy client.

# Jobs
Jobs are split out into their own branches so that when you pull down assets to work on, you get only what you need.

There are many ways these branches can be broken down. For this test, I will use 2 different approaches.

## Approach 1
Branches are split by Job #. 

```
Job1 (checkout here)
    |____Size1
        |____OptionA
        |____OptionB
    |____Size 2
        |____OptionA
        |____OptionB

Job2 (checkout here)
    |____Size1
        |____OptionA
        |____OptionB
    |____Size 2
        |____OptionA
        |____OptionB
```

## Approach 2
Branches are still split by Job #, but further split by the Size.
This doesn't seem ideal due to how similar the assets would be between sizes, but it would reduce
the size per pull.

```
Job1/Size1 (checkout here)
        |____OptionA
        |____OptionB

Job1/Size2 (checkout here)
        |____OptionA
        |____OptionB

Job2/Size1 (checkout here)
        |____OptionA
        |____OptionB
        
Job2/Size2 (checkout here)
        |____OptionA
        |____OptionB
```