---
title: "Assigning Conditionals to Variables"
categories: ["backpost", "ruby"]
---


One pattern I've been using a lot lately is assigning conditionals to variables in Rails. It's particularly useful when I'm translating a numerical identifier into it's human readable param.

Like parsing one of five difficulties in a game:

```
def set_difficulty
  difficulty = case params['difficulty']
               when 0 then 'very_easy'
               when 1 then 'easy'
               when 2 then 'medium'
               when 3 then 'hard'
               when 4 then 'impossible'
               else raise "Invalid Difficulty"
               end
 end

```

I just think that's a really elegant, readable pattern. Another good example is having two calculations, varying on input.

```
def file_taxes(filing_date, deadline, data)
  total_taxes_owed = if filing_date > deadline
                        file_late_taxes(data)
                      else
                        file_late_taxes(data)
                      end
  return total_taxes_owed
end
```

Again - it makes it simple to pass around the result of the conditional, while also being easy to read.
