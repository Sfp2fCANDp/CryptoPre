# CryptoPre

import csv
 
# Set up input and output variables for the script
ltcUSD = open("D:\\MachineLearning\\LTC-USD\\.txt", "r")
 
# Set up CSV reader and process the header
csvReader = csv.reader(ltcUSD)
header = csvReader.next()
Open = header.index("open")
High = header.index("high")
Low = header.index("low")
Close = header.index("close")
Volume = header.index("volume")

# Make an empty list
dataList = []
 
# Loop through the lines in the file and get each data
for row in csvReader:
    open = row[openIndex]
    high = row[highIndex]
    low = row[lowIndex]
    close = row[closeIndex]
    volume = row[volumeIndex]
    dataList.append([open, high, low, close, volume])
    
 with open('LTC-USD.csv', 'w') as out_file:
        writer = csv.writer(out_file)
        writer.writerow(('open', 'high', 'low', 'close', 'volume'))
        writer.writerows(dataList)


//CLOSE = The Close column measures the final price at the end of each interval. In this case, these are 1 minute intervals. So, at the //end of each minute, what was the price of the asset.

//VOLUME = The Volume column is how much of the asset was traded per each interval, in this case, per 1 minute.
