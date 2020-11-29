from riotwatcher import LolWatcher, ApiError
import json

api_key = '' #input your token here
watcher = LolWatcher(api_key)

print('Input your server: \nBR1 EUN1 EUW1 JP1 KR LA1 LA2 NA1 OC1 TR1 RU')
region = input()

print('Input your name: ')
name = input()

user = watcher.summoner.by_name(region, name)
user_rank = watcher.league.by_summoner(region, user['id'])
matches = watcher.match.matchlist_by_account(region, user['accountId'])
last_match = matches['matches'][0]
match_detail = watcher.match.by_id(region, last_match['gameId'])

print('Exporting user data...')
with open('user.txt','w') as o:
    json.dump(user,o)
print('user.txt created.')

print('Exporting user rank...')
with open('user_rank.txt','w') as o:
    json.dump(user_rank,o)
print('user_rank.txt created.')

print('Exporting matches data...')
with open('matches.txt','w') as o:
    json.dump(matches,o)
print('matches.txt created.')

print("Exporting last match's data...")
with open('last_match.txt','w') as o:
    json.dump(last_match,o)
print('last_match.txt created.')

print('Exporting match detail...')
with open('match_detail.txt','w') as o:
    json.dump(match_detail,o)
print('match_detail.txt created.')
