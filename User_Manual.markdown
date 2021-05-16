# Overview
XMReport is a light but very flexible and extendable template printing designer and engine, you can easily build template with complex layout. Most importantly, you can run the designer online, forgetting about the heavy and unportable JasperReport!

# Features
### Flexible Data Source Support
You can use the JavaBean, Map, JSON and ResultSet(QueryResult) as your data source, or event build it with scripts during the executing process, it is COOL!

### Economic Printing
With the Economic Printing enabled, the executed pages were trimmed and assembled into a new page, the new page has no header and footer. This feature can help saving papers if the content couldn't fill the whole paper.

### Snapping
We provide various of snapping features, which helps you design accurately and efficently. You can also turn them on/off in the snapping panel, current we support following snapping features:
1. Snap to the other widgets who has the same X or Y.
2. Same to the widgets who has the same width or height while resizing.
3. Snap to the position which has the same gap to the existent widgets.
4. Snap to the grid lines of page.

### Design Online
Yes, you can design and manage the tempalte online now, forget the heavy and out-dated desktop one!

### Extendable
You can customized your own widgets very easily!

### Light
It small, fast and elegant!

# Data Binding
In XMReport, every component support data binding, XMReport has a very flexible data-binding model, you can use JavaBeans, Map, JSON and QueryResult as the data source, and even a combination of them!
In fact, the data binding model of XMReport is just a stack, when encountering an variable in the data binding expression, or in the prepare/post scripts, the engine will do lookup in elements of the stacks, in the order of stack popping. 

1. The element is a JavaBean, the engine will search the getter method of the variable, then the public field member, return if found, continue otherwise.
2. The element is a Map, Map.get(variable) will be invoked and return if Map.containsKey(variable) is true, continue otherwise.
3. The element is a ResultSet, it it contains a column with same name of variable(ignore case), then ResultSet.getObject(variable) will be invoke and return. continue otherwise

![avatar](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL0AAACACAIAAADRUf8UAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAbsklEQVR4nO2dfUBT9f7H38CAaYgDhkwZCToFdcrI+ZRwhcSuD6iUaGhSeRUf6t5bXNQyszQtLX+JSHYltDJBMU3xgoUxAwUFYujEhTzmlKlDRx5lziOewe+PLXmQARt7Qvf663T4nnM+m+/Ozvme7+t8bZqammDFio7YmrsAKz0Sa26s6IM1N1b0wZobK/pgzY0VfbDmxoo+0MxdgCmgKEoul5Mk+fif2Gw2jfZUfAmGpUd+ZXK5nCAImUwmk8nUC3V1dQRBkCQpl8spipLJZCRJKhQKuVze9d2qM8RgMBgMBp1OZ7FYTCazb9++bDabyWQyGAz1gpOTk/E+Wk/BxmL7/UiSFIvFVVVVMpmsurq6rKzsUUooigLAHuDKdO3FcLZnezgw+jS6OVM0uyaWy32aXSPTWeFE15xdmAw49dJ+lAbI6h4t28kIFwCy273JBts7ChtCYUc+tJfdapDdUhJ3H8hq/wRAo9H8/PyYTCaHwxkxYgSTyfTz8/Pz83uq8mRBuZHL5SKRSCQSXbhwQSQSlZWV0ekOfkP6M13o3CG9B3rcZ7uTDMdrbPf7TAYYfcxTpKwOVVI7+T1P+d1e5VcdyyQq+Z8PxGXXFQolh8Ph8Xj+/v48Ho/H47HZbPOUaBLMmRuZTCYUCoVCYXFxsUgkIog/uX5s3rA+nv0aOZ5KLruGw1bSHcxVnW5U1UB81bNM6lL7p52oTCkSy2j2DjxeAI/HGz16NJ/P53A45q7RkJg6NxKJRCAQnDx5Mi8vTyqVcof7TA1i+nMU/MFXOJ5Kmp0pazEukusQXfYsrnTNzFOIxDUMBoPP58+ZMycwMJDD4fT0i3FT5IYkyczMzFOnTqWmpspksvFjfP8+8Znxw+v5gy8z+1LGProloFBCWOleUOZ+4iyVV/gHg8GIiIiYPHlyWFgYnU43d3X6YMTckCQpEAhSUlLS0tKcnukVFjp49t/IQL+ypyQr2lAokVPS/8fTbhknryruNYSHh7/yyivBwcEMBsPcpemAUXIjFAr37NmTmppKd6SFTX721Sny8b5Xe8qVismgVBCWO6UIPNMEcoVSFRkZuXjxYj6fb+66uoSBcyMQCDZs2FBQUBA4btBbcxE2tsIal06hVMg4y0j8n5sg9wqfz1+7du3UqVMt/ALIYLlJS0vbsGFDWdmlhS/5vj2nhut92yC7faqoktrFH/FJPiZj9Wdv3LgxIiLC3BVpxQC5EYlEMTExQmHR8vk+sfMqWS4PDFLZU4ucQPxR3+17a7jcUQkJCZb5y9Wt55oURa1Zs2bChAkcz/uVR7F1mdgamu7DZGDjovKadOX44YqgoMCYmJh2n6yZF/3PNzKZbP78+bIbV5PebwgcITVsWVbUCMv7RG92cWI8e+jQIRaLZe5ymtHzfCORSCZMmMDu13R+701raIwH37e+aM9VPy9iwoQJEonE3OU0o09uCIKYOXNmWOigb1eeodMUBq+pUxoe4u49NDxstfKzvThzof32ogrU3TFBXUaBZoekWHF4iP20aVN1erxvVPTJTVRUlDe7V9zS0zRbU/fgFYrBj4LjBPSbAscJmLQUpX9o/iQoxB/X2t9q9n/w1SGdj3X7LiqutlpDNuD1j0B/XudddZ+4tyr9BlJRUVHqsQBmR+fcZGRkCIVFB9ZVmD404mqELEPoWNSfBnkWd05hzHAELkFNbScbZn2F2IU6H+5gFnakNv/nlRt4fhGuynTej6HYt7ZafLE4LS3NbBW0QOfr4pCQkEAeNi7MMU49HREei8Ym/G9b63qWYehAJL6PKW/ijZkAIPgNA9yxeDYGeWra7EjFOC7GcQGgUIy9Gbj/AHNDMX1i835EFfguHbfvws8bS19GxRW8vh4ONATzMdoPi2bhyx9AswPHC2HvgDxrmk/clk3JPscLPPLz881z+Bbo1ilJkmRBQcFHb/Q3UjUd0NiIn84g9dO269+YiZXbkfg+AHy4CzMC8cIY/FoEfhSE+zTRST8NF2eM4+KQAP/8HOuW4Bk6VmzGm3Px7usAkPIzln2Kf87DOC7OXEBfJ9Qr4dQLLs4I8IX3AAD45zwAEPxmuo/8OKH+lzd8WVNeXu7o6Gi8o3Rl7KxuuVGPv/R2u9p5U0OjJPGQgotz2/XuLpATaGwEgJEc7FgFAFHTMXkFtqXgy9WtGv97K7bHYv7fAaA/E7P+g1VRAPDOF4hficWzAeDNuQDw4njs+lFz3rIcWG6gKMrPz8+oR7l8+bK3t3fHbXTLDYvFotPpkhuN3v1V+tdlNELHNS/PCMSxU63+WvoHZHXIKdbcdj2k8JDC+XI4OkBO4OUQk5aqH7I60Gh2YvHvRjrfSCSSkJAufRG65YZOp48fP/7k+crg57TcuhiN3nTY03D7btv1tXVgMmBrCwB9WwzwdemDG61vWq/LAWC0H+z+Gh02dgQGuOP3P9pua7EIimj80QG+vr7mLkR3nyE2NjZ68cJ358OptzHq0YqtLaZPxDf/w8svtFq/O615zYUKRE3XLBeXgTu4VcvRfgAwlgve0Fbr1U/sS6rarrc0FEokHnGMS1jdeVPjo/N9eFhYGH9s4PwPnSmT/1J9+hZ+LcLqHbh7DwBu38U7X6DiKj5comlw4ITmHFNTi4O/YGZQq81dnPFSCGLjNCetxkacOqdZ/8IYfPAVyAYAuHYT6o/WyxHSzu7wTUnUR3bcUaPDw8PNXQigX7/fvn3J4st9YuLoJo7O8EHITkR+CfpOAv15uIeiTIL8b+HZT9Pg4+UIXAz3UAyejajpWDSr7R72rINbX3i8COe/oXcgtn6vWZ/6Ke4/gPPf4BSEYRGa3Lz7OvIvghGMl1eZ6hNqJ2YbhOXOSXtSLGRcjp7PNSUSSUjwxMCRRNL7ZlAOGhuhJNGbrrmsaYOShIM9Wg5xn/ImXgtr/gnTtnnDQ1Aq9G4x3rfjA5kGSoUVmyEods0+XdzpbU43kUgkPj4+Xbmf0vP78Pb2zs45U3XLL2AhPU+k3z70x9YWTr21/lv2pqONF3FDDocW/5dq29zBvlVoOj2QCRCWYsxrNsJqHxOERif0/0q8vb1z8wrDXloestw2epOtnDBgVQbjk28w5U1clyOQZ+5SdISoR8w2BEXbBr6wIPdsiUWFBt0ct0Wj0bb+X1xRUXHZTX+fWXar4mFp6Qkdi7fm4dLh5msgy0dOYP3X8JphU1AxOCvr14Svki3QIDbAKZjH4+WeObcv5XCm8FmvGbYx21BV0/29GoZxXIQHw8PV3HV0jaoarPsvhrxkezDbI2n3N/lFVYFBk8xdVPsY7Kc7PDz8YumV9IwTwsv+w+bahCzD4ZOaO1srHUOpkJaDaf/GsAgbgchnX8qRi6XSyPlvmLuujjCaP5W0IzX1EN3hYVig6tVpGD8SViGmDZQKwlKk/Iy0UzaK+/aR82YsXva+HqPQxWKx+hUZ3S+p6/dTRvQ1CYKIi4v78WBiRXVtn96YNQmzJyGQB2ZP8hINj0KJnGL8+CvST6NeiRFDXWfMen3JsrcHDhyo664EAsFnn30mlUqLiooMcg1k5twIhcI9e5JSD+ynO1BhgQ/nTlYRCuSXIPUEZHUYPxJ/n4DxXPCHPy0ZUighvISCiziRjzwRGH0QMRnBfPR3wyEB0k7bK+7TIiPnL16yoivnG4lEkpiYuHv3bvWw0aysrNDQUIPUabbcCASCDes/KCgsCgywfyviQVhQ258nyXUIfsPxPBRchKwOvKEIHYfRw8AfBo6XAQsxP9KbEJVDeAnH8yCuglNv8IZizmQEjwbHq1UPE6VCRi4Sj9gJfmviP8ddu+4Tbb6mUCjcuXNncnLyo9GiYWFh6enphqrZDLlJS0vbsH5tWVn5wul4O1LV5pliu0hvQliK4ksQVUBYCsV98IaCNxQebvDzBndw2+/XkpFch7ga4mrU/okyCYSlAMAdDP5w+A8Bf3iXPktVDeIPIDmTxurvtXHT5498TYVCkZmZGR8fn5eX17I9jUa7dOmSAd+sY9LciESimJh/C4sKlr+sil3YyHLTcz9yAsJSiKtRfAniapRJQHeEnzeYDHAHw3cg1K/ZYveDGd+3JSdQJoGcgJxAtRTiasgJiKuhUILjBd5QjBgM/jBwB2tGCep3iPgD2H6Axh058v21G06fPr1r1y6Foh1vZPXq1StWrOjW52mNevyN0XNDUdS6deu2x32xcAZt47L7eiemXcgGiKtQJYVMjvIrqKqBrA5EPaQ3NQ0eBYjtAYYT3Big2YHdDwBYbqD/NbCJ5dbRrRzZADmheZBJPtAsy+pANuCOAkS9ZqWsTpMVSqUZZcxyA8cLvgM1C9zBBh5YQtRjQ5Ltzh9sXN3camtvdr6B4TBubmQy2fz5kbIaUdKaOybuxZcTmgA9Wnj0b6x+yaP0JigVFErd+q/VaWM4gdEHdEcwGWC5oa8TWG5guYHRR7NgyoFHwlJEf0q3pQ8eNoJ37NixNmcdd3d3gUDg7PzY4Nnu0ZXxxd14Hh4yKXAUmfTeTcvvmKFUWkfSsJiW3rFEqbBii4PgnNux/2X+8ssvO3fubClurly5cuvWraavSp/cEAQRFPR88KibcW/X9ZTr1o5peAiyAXQHONi3Wv/ZXgTyMNG/bXtRBbw84NbXZAUiZpttZvGzuXlFTCZTIBAkJiampaWp76rOnz/P45n6sa2+vma/O3qH5vWPYMOHDR8O48Gdh+379dlJ13lcu2xJBwIotDughhJAu07cfxr9PGujFs6nKCo0NPTQoUOXL19+7733WCxWTEyM6SVOvXzNorMH1l/vzplm4XQ8yIf8JGJexQf/xddH9N9Vp7TRLltiXgFUV/atvy8u+e2Rr8lmszdv3nzjxo3Y2FixWKz/fvXCbv369TptsGzZsvBgaurYP/U+ZFoObGwQMRmODnjOD+VXUCbBvClQKHFIgISDOJYDlQrDfDTtd6TCxRkllfg4CfVK+A9BoRiffoPDJ+FgjyHPNjdz64usQnyRjF8K4OUBDzfkl+DdBNTIUHoZtXUIaC0CLP0EPp7Y86Hm58nRAS+OR+ZZ/P6HZmzyvuMI8MXFKsTtR1EpfAZoBK6Un2FP09y7tVsMAFEFtnyHAydQJsHwQbhQ0VElXcHBHsoHdnt/rFqyJLrl+qFDh5r+FSd6+ZqvGnKIq62tZkCd4Df8dAbTJ+KOAss+hZzA0pcBIP00LlTgfDlem4Ghz2p1LtNP4/vj8B+CF8YgvwT8KJSktqNdPqIrAii0OKAGEUD1IJSv3JBYbGxfU03Hd1V6+Zoe3S4KwF//ckezkfQBAIQHIzxY86c/ruGXAk1uABSV4lyKpr81PLYd51KdvAHu2PMhAERNx/ly/FKAf0dq1S47FUDV++zYATWxAMpyA0WpjO1rqum4F0cvX/NWH+8Bt7pTU8rPOJgFioJnP2z5F+b+9VQuvwRVUty7j/PlrUS4f8zShEabczl6GABMndC8SX+m/hehLenAATW9AGpsX1NNV6xNvXxNUX2wf7dy88qLSHwfdMfmRzaNjZjyFm7fxRsz4eEKjhdutXghqdtfj821OZdq+jyjQw1dEUDRoQNqegFUcM6dzx/UY33NJf94dx7NqZf+9340u7a9rj+dwZkLIHI0vXC5WhwJbc6lHnRFAEWHDqiJBVCFEok/UnHxKw25U33Ry9ccM27+x4MNLt01NqL+HgBUXMXR7PbbaHMuO6AD7bJTARQdOqAmFkCjPmZyR43t0b7mPnHlg5ivhhswOtMnIiwIntPg+gIWrMVH0VpbanMutdGBdtmpAIrOHFCTCaAx8QzhJfukpN0939cMCQkc3Scp9qIBn+88bkxqQyeTstPGnTZo44CaUgClVFixtZ9ASM/OPmUai6oro3C64WtmZ1ddeybg9QF5JQa7AnzcmNSGTiZlp407bdDGATWZACosxZhFrsKq/iYLTRfpnq+Zmxs2e0HIUjJ6q4+lGXdGwmQCKFGPmHjXoKUOgS8syM3Ns6jQwAC+5tatRUVFZdc8fWb3WrWz3xOfHhMIoHIC6/c4e4U5FlRysrJOJiQkdOAqSCSS9evXtzsa0KgYyNfMzd2XvD+zqJ9XmEPMl96W42saHKMKoFU1WPc1Y8ic3gez+yft/i4/vzAwMLDdlhRFCQSCRYsWDRkyhEajmV4ENsr8U/n5+aOGOr4TeX/elCYLHxVlCVAqHDuF7QccC0oe8sfw165d18H8UwRB7Nq1KzExUT16i8PhXLx40bCTLXblutgIN3VND4CmWjn55pamd3cgLAhWX7Ndmn3NHBD1cOn7oAk2UN3T1l6tTe3atYsgmq8G4uLizDJDp8Fy0+zBTGv67/5G7mCQDRAUIuVnTPsXnHojLMjqawItfM2MXCiUCA9GwmoEjwajD6pqmuIP/B716kssFmvjJ3FqD4YkybS0tJSUlMzMzDbjsyZNmsTlcg0+30dXdmggD+adfwmFhdo8GLIBmWdx6pzV12zla04ei8e9RDR7MLbDh/k9N+ZvGRkZUqkZZtzp+HfKUB6M3cZlZFc8GKuv+biv2S5EPTYk4atDtj4+g65dl7V7x3TkyJGAgACjVN/Z+JvueTCRc2XSC0lr6vXrzLD6mp0iLEX0JzS6s9+L017+/vvv2/yCcDicS5cumeXJQ/c8mJH3ktbUGeqC1+prtgulworNtoJzzOxThWKxOD4+Picn59GFzubNm9977z3DHEkX9PVgAicE+98yqgfzlPuabYjZhkyhV+6Zc0wmUyqV7ty5U/0+CjqdXllZyWazjXjs9tAnNzNnzsS9oqNbas31I/L0+JoteWmVPWk/Mf14lvqHiSTJ1NTUvXv3MpnMQ4d0t3K6h865ycjIiF7yWuWh2+b6+vSgR/uaj1AoMewVp7gd37aZV1wsFrPZbAbDpLemes1bNuLaxkWVRirISgds+sbh+Dn//HyzToIFQNfckCTp4uLy8w6b4OfuG68mK9oouIigaKOPS1djBA/Gguaxfrro6R4Mw3uA+eYnfYqR1YFGo4nF4p7pwZQ0BPtbc2MGBOc9+XwvS/BgdB5/Exsbu/tglYLURVWyYggUSiQeJmNjY81dCKCnB8MfawwPxhi8l4CUnztabrnSwonaxOaO4vdwD6bibsyuMZYfnT3HkJHb0XLLlZZMzI7+wtJGy/Fg9CmCwWBkZ2eHhIQQ9WOSYs/T7U390p6uU5La/FasdpdbrrRMKBVWbPMRFDbm5uaY/nmCNrrnwUjtAl7vn3fRcr/4/szmV6+1u9xypQUivGQ35h8sYblzdnaORSkN3fZgZr0SEn0v+ovh8jsWcf58YiDqEZPADoqmBYZEPLkeTI2rz2yHVf/1euI9GBMgJ7D+W5ZXGL2g3DMrS9CxB2MuDOfB7EvJLOzrFeYQs3NIlbSHjLayMKpqsG53/yFzeh882Tdp97f5+QXaPJiWUBSVkZFhgvJaYtB5yy5eTE8/Lqz08JsD3kKnpKM21nnLugKlwg8Cm+eXPOMXYScQDdyXfPDiRXFkZGSnG0okkjVr1vj4+Jj+vZDGuii5RdjHbLNdt0s10+rBaKGlB3O73sbV1R4gu7itQCCIj49XGw4cDmflSlO/FMdg55u0tLSAgICZM2f6DXwg+sHlWsZt+UnV7g+gUGLav+A1HYs2IC3H4iZuNT0KJTJysWgD+v8dIcsgJ5CwGtKfGq8eI8qO0Pi+d6MWLhg5cuThw4cf31Yul2/ZsiUgIGDKlCkZGRnq0aJxcXGm79Qx1HwwMUJh0fKF/rERZSxG21fUWj0YnT2Yo8O2773C5Y5KSEhQz2QmFAoTExNTU1PbiA3h4eFHjx41bLVd8TUN4cFs375w7tiNiypZzjc6r8nqwXTdg9nH3bW/8vnnJ9bW1v7++++Pt3F2ds7JyXFxcTFs5V2ZTaib88HMl92oSfrIOXDoeT32YPVgOuX0BadX1znK/7xHkl299DEURsmN5n1b4wYn/UdEt6vTv7oWWD2YdqFUWLY9IF0g5fP52dnZbQIUERFhpPlgDO/dEQQRFBQUPIEdtzSPZmOsN69YPZiWxHw1PPNs47Fjx/bv35+YmCiTNY9/MuC8rF1HXw+Gkh/dKKLZmPrkqeYp9WA+8CXhk56eTlFUcnJyfHy8utuGx+MVFRWZ+JZKLw8mekllGs2J1t4MOxbJk+PBzO8Xt33nIw8mJyfn4MGDycnJCQkJb7zxhimL0cuD4WHjwhzj1GOlIzal+B7Pd8nPz2+5Ui6Xp6amLl++3JSnHL08mF3sYG6V8Wqyoo0CsV3QEpv6+nqzvCupJbr1F2s8GLfLRqrGSsewXFUURbW8KDYXuuVG48Hc6CGdKk8c6vlgTD9L2ePolhuNB3PevfOmVoyAoIjGH/2c2X+koKcH86NCoTRGMVY6QqFE4hHH2JWrO29qfPTrvwlD/amjnyt6ykOAJ4OXVtmR9hPTj5+0BKVBz/7iAB43bEJdXAxpjY5piNmGwzku+YUlFqI06DP+hsFgZOfkZeS7LvrY0Tqiz9hQKkRvQlqua+6ZcxYSGnTLg8k5U3XLL+BVhzwtc9NZ6T7CUox5zUZY7ZN9utiilIbueTBnhGEvrwhZbhu9ydY6kM+wEPWI2YagaNvAFxbkni2xqNDAAB7M/20vKiouqx3hM8t2Vbx1GKgBkBNY/zW8ZtgUlHtnZf2a8FWyBXowBpvXI+3oj+vWvl31x/Xlc5remvukDd4zDVU12JuBL3+wYXm4frTh88gF/zB3RVox9HwwWSc2fPh2QVFFIK/prXntj5+10gZKhYxcJB6BoBB8ntfadVumzphnCTfbHWDg3KgRCoV7dn2Seugnuv3DsKAmqwfTLi09GAVJi5wTvHjFJv6YcZ1vaQEYJTdqSJIUZP2U8t0XaccLnHo1hQU1WeeDQZv5YO7bhk8b9cqCpcFT5pv4RbLdxIi5eQRJkpk/p53KSk49nCO7dc/qwTCcHSNmjZk8dUFY+CJLeNikB6bITUskEokg8+Dx9EMFRaWyW/efFg+mGk697XkjvefMeSk4dAFn6AgLv3zpFFPnpiVSqVRYcKK48IRIJBJeuKq418Ab2vSkeDA2sLHj+rrzn+P6jw7ij5/1BGSlJebMTRvkcrmwIEss+rW4uEhcKimrvkt3hJ93U0/wYGwUyibOwGd4XM8RI0bwx03m8kK9B5n/rZ/Gw4Jy0waSJMVicVX5edn1y+Vl56qqqmW1BHFHIZVpJAqzeTA0G87AviwPBmewt+8wf1b/QRzf0dyR/hbYO2c8LDc3HSCXywmCkErOy2uvELdrpTXVdwiCIG6TDx7KausASG/cpahGhVIlv/2w67tluTvQHR0Yzg6Mvs/Q6Y5MN2eWR7++DCZrwEDWgEEMV2/WgGdZLNZTlQ9t9Mjc6ApFUdqmqFSPfDVxPU8AT0VurBgcg73/xspThTU3VvTBmhsr+mDNjRV9sObGij5Yc2NFH6y5saIP/w9lpcStP2PNbwAAAABJRU5ErkJggg==)

Data binding script starts with '=' or '//javascript' will be evaluated as script, refer to the script section for more details. it is just a pure string object otherwise.

If current widget is a container such as Cell, Body Header, Footer, Page or Template, it will push the data into the stack, so that the child widgets can access to the data of their parents.

# Executing
Executing means the process of converting the design widget to the print widget with provided data source. within the same container, widgets are executed in the order of 'z' property(zIndex), widget with lower z will be executed first, if there are widgets having the same zIndex, the executing order of them is undefined(random). 

![avatar](data:image/png;base64,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)

The executed widget are output to an execution context and you can see them in later executed scripts with the name of widget, note that widgets not executed are not visible since they doesn't not exist. If a widget was executed more than one time(such as grid, row and cell), then the latest one will be visible.

# Widgets
There are 8 build-in widgets in XMReport: Page/Header/Footer/Body, Text, Barcode, Image, Straight Line, Grid, Cross Table and Customized Widget.

## Page/Header/Footer/Body
Page is the top-most container, within which are the Header, Footer and Body. They will push the binding data into the stack, so the rows and cells inside grid can search it first. Header and Footer are a little special, they will be newly executed every time even if they has components with imcomplete execution.
Note that when nothing was selected, the settings in DataSource and Script panels are applied to the Page.
The specific properties for Page, Header, Footer, and Body can be set within the 'Page Setting' panel.

## Text
Text widget can display text within the rectangle of widget, which has special properties such as paragraph style, font style, and date format.

The paragraph and font styles are mostly the same as which in MS Word, but rich text was not supported currently. 

You can set date format to display the value in a specific way just like MS Excel.

## Barcode
Barcode widget can encode the value into a barcode, which can be easily processed by machines. 

Note that there is a special property named 'dpi', to print the barcode accurately, the dpi must be consistent with the device dpi. Some device might have a very lower dpi or the barcode zone is very small such as printing tags, incorrect dpi will cause the error in machine scanning!

## Image
Image widget is used to display a picture, the data of which can be in the following format:
1. An byte[] object of the picture.
2. A base64 encoded bytes with 'data:xxx/xxx;base64,' prefixed, for example: 'data:image/jpeg;base64,xxxx', the content from the first comma ',' on will be decoded to an byte[] object.
3. An url, the engine will try to fetch the resources.

## Straight Line
Just a simple line, binding data was ignored.

## Customized
You can extend PrintWidget and print the widget in your own way, specific the fully-qualified class name of your PrintWidget or Executor in barcode setting panel.

## Grid
Grid is a container for rows, it will push the binding data into the stack, so the rows and cells inside grid can search it first. The grid is much like the Table in MS word, you can merge, split the cells. The Grid widget is powerful but some what complicated.

### Grouping
Group is not a widget, grouping means dividing a list of row data into several groups, which is often used in grouping the QueryResult. as following, the data is divided into 2 groups by the field 'BillNo', note that the group1 and group3 were in different groups since they are not  together.

|BillNo   |Creator    |MaterialName   |Amount   |
|:-------:|:---------:|:-------------:|:-------:|
|20180101 |Mosmith    |Paper          |120kg    |
|20180101 |Mosmith    |Pen            |100      |
|20180102 |Mosmith    |Notepad        |200      |
|20180102 |Mosmith    |PC             |10       |
|20180101 |Mosmith    |Keyboard       |20       |
|20180101 |Mosmith    |Mouse          |20       |

Groups can be nested, as following: there are 2 OUTER GROUPS divided by BillNo: 20180101 and 20180102, within group(20180101) there are 2 groups divided by Requestor: group(Mosmith) and group(Andy), similarly group(20180102) has 2 sub-groups group(Andy) and group(Dall). Note that the group(Andy) in group(20180101) and the group(Andy) in group(20180102) thought they as the same group value, we use 'INNER GROUP' or 'SUB GROUP' to denote them. Obviously, OUTER GROUPS starts prior to the INNER GROUPS, and INNER GROUPS ends before the OUTPUT GROUPS.

|BillNo   |Rqeustor   |MaterialName   |Amount   |
|:-------:|:---------:|:-------------:|:-------:|
|20180101 |Mosmith    |Paper          |120kg    |
|20180101 |Andy       |Pen            |100      |
|20180101 |Andy       |Notepad        |200      |
|20180102 |Andy       |PC             |10       |
|20180102 |Dall       |Keyboard       |20       |
|20180102 |Dall       |Mouse          |20       |

### Row
Row is the most complicated widget, there are 4 types of rows, Simple Row, Group Start Row, Group End Row, and Detail Row.
Note that rows are executed one by one from up to down, so you couldn't see the future rows and cells.

#### Simple Row
Simple Row is simple, it is just a container for cells, it will push the binding data into the stack so the cells inside it can search it first. If 'appear-in-every-page' is set, it will be newly executed in every page.
#### Group Start Row
Group Start Rows should be placed right before the Detail Row. Note that no other types of rows should be between the Group Start Rows and Detail Rows.
Group Start Row has a property named 'Group Field', Every time before the Detail Row being executed, it will lookup the object with name 'Group Field' in the stack, we denoted object with name 'Group Value', if the Group Value changes or OUTER GROUPS starts, the Group Start Rows will be executed.

Note that the data of Detail Row was pushed into the stack before executing the Group Start Rows.

#### Group End Row
Group End Row, contrast with Group Start Row, should be placed right after the Detail Row. Note that no other types of rows should be between the Group End Rows and Detail Rows. Group End Row has a property named 'Group Field', Every time before the Detail Row being executed, it will lookup the object with name 'Group Field' in stack, we denoted object with name 'Group Value', if the Group Value changes or OUTER GROUPS ends, the Group Ends Rows will be executed.

Note that the Group End Rows were executed before Detail Row pop the data from stack.

#### Detail Row
Detail Row is a special kind of row, whose binding data should be iteratable or an ResultSet object. The engine will iterate over the binding data, in each iteration, the the Detail Row will be newly executed, until the iteration ends. The Group Start Rows and Group End Rows reply on the Detail Row, there will be no execution of Group Start Rows or  Group End Rows if there is no Detail Row.

### Cell
Cell can be a Text widget or a container for other widgets, it is a Text by default, you can change the type in the Grid/Row/Cell properties panel. It has the same properties with Text widget when the type is Text. You can place other widgets inside it when the type is Container, double-clicking it to edit the child widgets of the container

### Grid Computation
Like MS Excel, you can perform some grid computation such as Sum, Average, Count in Grid widget. there are several example:
but there is some differences.
1. The Cells or Rows performing the grid computation should be place in later rows after the target cells of computation ends, since you cannot see the future cells. If you want to place the computation result before the target cells, please place a the Post Script to a later cell or row, for example: 
```
targetCell.setValue(sum("cellToSum"));
```
2. The target cells are denoted by the name of top-left and bottom-right cells, for 
```
sum("cell1', "cell8");
```
3. There are 4 kinds of computations: normal(global) computation, group computation page computatin and row computation. normal computation will collect all executed cells, group computation collects the executed cells within current group, page computation collects only the executed cells of current page while row computation .
	1. sum/average/count（global/normal）
	2. gsum/gaverage/gcount（group）
	3. psum/paverage/pcount（page）
	4. rsum/raverage/rcount（row）

You can use the 'getPageNo()' and 'getTotalPages()' to fetch the current page number and number of total pages. 
Note:
1. When you evaluate them within the group row or the children of group row, it will return the current page number and number of total pages of current group.
2. When you evaluate them within grid or the children of grid, not group row, it will return the current page number and number of total pages of current grid.
3. Otherwise, return global page number and total pages.

In fact, the 'getPageNo()' and 'getTotalPages()' redirect to the real methods according the current widget, you can call the real methods directly also:

1. getGroupPageNo()/getGroupTotalPages()
2. getGridPageNo()/getGridTotalPages()
3. getGlobalPageNO()/getGlobalTotalPages()

Note that 'getTotalPages()' does not return a number since we don't known how many page until the end of execution, instead it returns a placehold string, which will be replaced by the number of total pages after execution.



# Cross Table

Cross table was something more like the CrossTab in JasperReport, but the Cross Table in XMReport was more powerful, easy to setup and flexible.



# Script
There are 4 kinds of scripts for each object: 
1. Data Binding Expression
2. Prepare Script
3. Post Script
4. Final Script

They are evaluate in different stage , and they should be written in javascript. The return value of last statement will be treated as the result of evaluation of the script. while Different widget might have some different build-in objects or methods within the scope of evaluation. following are some common objects and methods.
1. designWidget: is the runtime object of your design model, you can access to the properties applied within the design stage. Note that there is only one Design Widget object for each Widget.
2. printWidget: is the object that performs real printing function. A designWidget will be converted to one or mode printWidgets during the executing process, you can access to the PrintWidget that is currently converting.
3. executeContext: There is only one ExecuteContext object and it lives thoughtout the whole executing process. If you want to record something and use in later widgets, put it into the executeContext and get it later using the setProperty()/getProperty() methods. Or event you can change the data stack with method push()/pop().

And you can also interact with java objects in the script, and the packages 'java.lang' and 'java.util' are imported by default, for example:

```javascript
//javascript
importPackage(java.io);
var fs=new FileInputStream("d:/test.txt");
var sb=new StringBuilder();
try {
    var br=new BufferedReader(new InputStreamReader(fs, "utf-8"));
    var line;
    while((line=br.readLine())!=null) {
        sb.append(line);
        sb.append("\n");
    }
} finally {
	fs.close();
}
sb.toString();
```

### Data Binding Expression
Data Binding Expression is used to determine the data of widget, the evaluation result of the script will be bound to the widget. Of course you can build it instead of finding in the data stack. Data Binding Expression is executed before the Prepare Script.

### Prepare Script
Prepare Script is executed before engine converting the data into widget secific data(for example: engine will convert the data into string according to the date format). So you can do some operations to PrintWidget or binding data. The evalution result of the script is ignored.

### Post Script
Post Script is executed after the engine converting the DesignWidget into PrintWidget, and before the binding data pop. So you can do some modification to the final PrintWidget. The evaluation result of the script is ignored.

### Final Script
Final Script is executed after the whole converting work done. Since you cannot see the future executed widgets, after the whole converting work done, you can see result of whole execution. For example, the total pages, we couldn't know it until the converting work done. You can record/count something the executing process while fetch them in Final Script. The evaluation result of the script is ignored.



# Data Source

Data source is something assistant to template designing, you can do the data binding with drag and drop if you have a data source template.

XMReport does not restrict you to a specific type of data source, so we only provide a way to describe your data source. Note that while generating the template, the engine will still use the data passed in by you. You can define your data source with following formats:

1. Simple-Mode, start with "/// type=demo", and write a JSON with following format:

   ```json
   /// type=demo  
   {  
       field1: 'expression of field1'  
       field2: {  
           subField1: 'expression of subField1',  
           subField2: 'expression of subField2'  
       }  
   }  
   ```

2. Or if you have a demo data:

   ```json
   /// type=demo, ignoreValue=true  
   {  
       field1: 'expression of field1'  
       field2: {  
           subField1: 'expression of subField1',  
           subField2: 'expression of subField2'  
       }  
   } 
   ```

   

3. Comprehensive-Mode, each field need an element to describe.

   ```json
   [  
       {name: 'field1', expression: 'expression of field1'},  
       {name: 'field2', expression: 'expression of field2'},  
       {name: 'field3', expression: 'expression of field3', children: [  
           {name: 'subField1', expression: 'expression of subField1'},  
           {name: 'subField2', expression: 'expression of subField2'}  
       ]}  
   ] 
   ```

And even more, you can define how to decode the template, and then return a Comprehensive-Mode format to XMReport, by define your decode function in designer.html, like following:

```javascript
window.config={  
   dataSourceTemplateParser: {  
       accept: function(content) {  
           if(content.indexOf('/// type=ckey')==0) {  
               return true;  
           }  
           return false;  
       },  
       parse: function(content) {  
            var model=eval('var model; model=' + content);  
            var ckey=model.ckey;  
            // process via ajax ... jQuery is window.jq  
  
            return {  
                expression: '='+ckey,  
                children: [  
                    {name: 'field1', expression: 'expression of field1'},  
                    {name: 'field2', expression: 'expression of field2'}  
                ]  
            }  
        }  
    }  
}  
```



# Advanced Styles
It is redundant to introduce so many styles here, much of them are similar to the MS Word, only some special styles are described here.

### Data Format
Like excel you can display the data in different formats.

### Cells Filling
Cells Filling are usually used in Chinese voucher. We support this feature, you can set it in the paragraph panel.

### Appears in Every Page
Mainly used to build grid header, bill header and water marks.

When enabled: 
1. If the widget was executed completely, it will be executed again in next page.
2. If the widget was not executed completely, it will be continue executed in next page.

### Allow Crossing Page
If a text or cell has a lot of content to fill, but the page does not has enough height, the rest content will be displayed in next page display when allow-crossing-page enabled.

### Economic Printing
With the Economic Printing enabled, the executed pages were trimmed and assembled into a new page, the new page has no header and footer. This feature can help saving papers if the content couldn't fill the whole paper.

# About the Demo Project
The demo project contains something about the SpringBoot, you just need the following code run the engine.
```
import java.io.FileInputStream;
import java.io.InputStream;
import java.io.Reader;
import java.io.InputStreamReader;
import org.mosmith.tools.report.engine.output.ReportHelper;

...

Reader templateDataReader=new InputStreamReader(new FileInputStream("test.template"), "UTF-8"); //　Template Data
Object previewData=new Object(); // Data Source

ReportHelper reportHelper=new ReportHelper(); // Helper tools, refer to the implementation of ReportHelper for more details if you want to do some customization.
InputStream pdfIs=reportHelper.toPdf(templateDataReader, previewData); // Execute and return the InputStream of Pdf file.
...
```



# About the License

You can use the XMReport free even for commercial purpose, but there is no guarantee and service. So it would be better to purchase a license if you want stable and long tern use, we can provide forever license and source license.



# Q&A

1. Error message was not shown completely

   Since error message contains the stack trace, it would be pretty long so you need to set global property to enlarge the message length limit before the execution of the script: 

   ```
   set('exceptionMsgLengthLimit', 50000);
   ```

2. Generated PDF that contains images is very big

   You need to enable the 'Convert to JPEG' for Image component, and if you have images in Header and Footer, you might need to use the following code in your Post Script to reduce duplicated image bytes:

   ```
   1.printWidget.setProperty("pdfImgSerialId", "image1"); // Reused ID 
   2.printWidget.setCacheImgInExecuteContext(true); // Cache it 
   ```

   