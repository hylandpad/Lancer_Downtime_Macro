# Lancer_Downtime_Macro

This macro is meant to automate downtime rolls and create a report that can be added to a player's downtime journal so the player and GM can track assets gained, lost or changed from downtime activities.

Customization

--You can add custom activities to the macro for your campaign. You will need to add a new object to the Activities array to do so. The object model looks like this for a non-rolled activity (such as Power at a Cost or Get Focused):

{
  Name: "Power At A Cost",
  Rollable: false,
  Results: {
    0: {
        ShortDesc: "Success",
        LongDesc: "I'm resourceful, I can get what I need... or something very near to it. It's just a matter of time, manna and how much I'm willing to stick my neck out for it.",
        Info: "<p>Name what you want. You can definitely get it, but depending on the outlandishness of the request, the GM chooses one or two:<ul><li>It’s going to take a lot more time than you thought.</li><li>It’s going to be really damn risky.</li><li>You’ll have to have to give something up or leave something behind (e.g., wealth, resources, allies).</li> <li>You’re going to piss off someone or something important and powerful.</li><li>Things are going to go wildly off-plan.</li> <li>You’ll need more information to proceed safely.</li><li>It’s going to fall apart damn soon.</li><li>You’ll need more resources, but you know where to find them.</li> <li>You can get something almost right: a lesser version, or less of it.</li></p>"
        }
      }
  }

  --Activities that require rolling require a bit more configuration

  {
    Name: "Buy Some Time",
    Rollable: true,
    Results: {
                "0-9": {
                    ShortDesc: "Mild Success",
                    LongDesc: "The situation is deteriorating quickly. Whatever I'm running from required some sacrifices to escape - or maybe I didn't escape it at all.",
                    Info: "You can only buy a little time, and only if drastic measures are taken right now. Otherwise,whatever you’re trying to stave off catches up to you."
                },
                "10-19": {
                    ShortDesc: "Moderate Success",
                    LongDesc: "My situation has improved, but not by much. I bought a little time - for now. Next time, simple measures like this won't suffice.",
                    Info: "You buy enough time, but the situation becomes precarious or desperate. Next time you get this result for the same situation, treat it as 9 or less."
                },
                "20+": {
                    ShortDesc: "Monumental Success",
                    LongDesc: "I got the time I needed, and then some. Whatever was dogging me has abated - for now.",
                    Info: "You buy as much time as you need, until the next downtime session. Next time you get this result for the same situation, treat it as 10–19."
                }
            }
        }

Flavor Text in Report

--The script has alternative styling for people who want a more generic or unflavored experience. Locate the termSet function invocation and change the argument from 'diegetic' to 'rulebook' to have most of the fluff stripped from the report


TO DOs for V4:

--Better incrementing logic for journal entries in downtime folder
--Render journal entries after they are logged to the journal
