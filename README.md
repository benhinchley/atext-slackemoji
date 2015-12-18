# atext-slackemoji
 I found myself doing this `:bowtie:` in like every app, and well I was getting annoying that it didnt work outside of Slack, github etc etc etc so I spent sometime and made it in [aText](https://www.trankynam.com/atext/)

I have saved it here as both a `.atext` file and a `.csv`.

Thanks to [http://www.emoji-cheat-sheet.com/](http://www.emoji-cheat-sheet.com/) for all of the keyword bindings to emoji for the original version.

Current version scraped from [https://www.emojibase.com/] via JS

    var output = '';
    $('tr').each(function(i, row) {
      if ($(row).find('td').length > 4) {
        var short = $($(row).find('td').toArray()[2]).text().trim()
        var emoji =  $($(row).find('td').toArray()[4]).text().trim()
        if (!!short && !!emoji && (short.indexOf('N/A') == -1)) {
          output += short + ',' + emoji + ',' + '\n';
        }
      }
    })

    var textArea = document.createElement("textarea");
    document.body.appendChild(textArea);
    textArea.value = output;
