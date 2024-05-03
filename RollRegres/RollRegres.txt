# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Rolling Regression Use roll_regres (rollRegres) With (In) R Software
install.packages("readxl")
install.packages("httr")
install.packages("devtools")
install.packages("pkgbuild")
devtools::install_github("boennecd/rollRegres")
library("httr")
library("readxl")
library("pkgbuild")
library("rollRegres")
# Import Data Excel Into R From Github Olah Data Semarang (timbulwidodostp)
github_link <- "https://github.com/timbulwidodostp/RollRegres/raw/main/RollRegres/RollRegres.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
RollRegres <- readxl::read_excel(temp_file)
# Estimate Rolling Regression Use roll_regres With (In) R Software
Rolling_Regression <- roll_regres(y ~ X1, RollRegres, width = 5L)
Rolling_Regression$coefs
# Rolling Regression Use roll_regres (rollRegres) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished
