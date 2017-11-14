# Analyze Facebook Reactions with R!


library(Rfacebook)
load("fb_oauth")


fb_page <- getPage(page="PASTE_YOUR_PAGEID_HERE", token="PASTE_YOUR_ACCESS_TOKEN_HERE", n=100000, since="2017/10/01", until="2017/10/31")

reactions <- getReactions(post=fb_page$id[1-100000], token="PASTE_YOUR_ACCESS_TOKEN_HERE")
write.csv(fb_page, file = "fbposts.csv")
write.csv(reactions, file = "Reactions.csv")
