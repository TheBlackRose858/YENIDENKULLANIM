import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'{bot.user} olarak giriş yaptık')

@bot.command()
async def malzemeler(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, işte kullanabileceğin malzemeler: plastik, cam, kagit, pil, yiyecek ve straforkopuk!')


@bot.command()
async def plastik(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzeme ile -özellikle bir kap haline getirilebiliyorsa- bir saksı yapabilirsin! Çiçeğinin de senin de yüzün güler!')

@bot.command()
async def cam(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzeme ile gerekli önlemleri alacak şekilde çiçek, kelebek ve çeşitli böcek şekillerinde süsler yapabilirsin! İple uygun bir yere assan ne harika olur!')

@bot.command()
async def kagit(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzeme ile -özellikle birden fazla atık kağıdın varsa daha kalın ve dayanıklı olur- çeşitli şekillerde süsler yapabilirsin! Odana renk katar! ')

@bot.command()
async def pil(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzeme ile -eğer sağlık tehlikesi içermiyorsa- bir roketin motorlarını yapabilirsin! Oldukça kullanışlı olur. ')

@bot.command()
async def yiyecek(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzeme eğer meyve ise onu yeniden ekebilir ya da bir şekilde kurutarak evini süsleyebilirsin! Ne doğal yaşam tarzı ama!')

@bot.command()
async def straforkopuk(ctx):
    await ctx.send(f'Merhaba! Ben {bot.user}, bu malzemeler ile Güneş sistemi modelindeki gezegenleri ve Güneşi yapabilirsin! Harika olur!')

bot.run("token")
