# Idea: Have a model of Internet energy consumption

Some challenges: 
   * bits don't cause energy. capacity causes energy!
   * are protocols a problem?

how is energy divided up?
   * network
   * end-users
   * servers

(click clean report by greenpeace had some numbers on this. I think it was 25% is the network. #TODO look this up)

Considerations for networks:
   * much of the Internet is powered by fibre. ie. lasers. These will use pretty much the same energy with 0% utilisation as with 100% utilisation.
   * submarine cables: giant lasers, with repeaters (devices that regenerate the optical signal)
   * things happening in routers that are not powering lasers
      * is this significant?
      * BGP routing?
      * filtering/firewalling?
   * green-ness of the energy that the network is using is determined by the physical location. data-centre (does it do green energy, generate it's own (solar/wind)?)
   * those that have equipment that uses significant power can choose to offset this (cloudflare does). this is prone to "greenwashing", just to make the claim that an org is "green".

Considerations for end-users:
   * When you buy an Internet service, you get a certain "package", ie. what technology (fibre,dsl,cable,mobile) at what speed and/or data cap.
   * What is the boundary of "Internet use"?
     * Netflix is considered Internet use. What energy does the home component use? determined by the devices in your house. The effect on Internet energy use is very indirect. Since the network is already procured the energy on that is already spent (because the lasers will be powered even when you don't use them). But your usage is going to influence future procurement. If links saturate netops will upgrade them or add paths/interconnections and redistribute traffic over old+new paths/interconnections.
   * What is the efficiency gain that can be made in apps? browsers? (these are considered Internet use? to what extent?)
   * What is the efficiency gain that can be made in protocols?
   * What is the efficiency gain that can be made in web-site design (minimise complex features (javascript), simple html, remove ads?)

Considerations for servers:
   * What is the boundary of "Internet use"?
     * If facebook does massive machine learning to predict Internet user behaviour, this likely takes a lot of energy, but is it "Internet use"
     * If google, after scraping the web for content, does it's page rank algorithm, is this "Internet use"?

How do these interplay? 
   * CDNs put content closer to the user, so they use less Internet capacity. CDN filling the cache can be done when energy is available/greener.
   * which Internet use can be time-shifted, since emissions caused by energy production can be drastically different at different times of day/season

Fixed internet vs. the rest
   * For mobile networks (and satellite?) BW-cost per GB could be different from other technologies. For sending data through the air I suspect that it does make a difference for the technology if you send bits or not (as opposed to fibre where it doesn't make a difference).

Is there a good overview of these types of energy profiles? (ie. what technology has what energy profile. , what are the major parameters influencing this profile?)

I think a lot of research is built on oversimplified or wrong models of how Internet energy consumption works.

Energy efficiencies caused by Internet
The Internet consumes resources (power) but it also can save some resource use. At least 2 classes of this phenomenon:
   * excess heat (data centres) being used for city-heating, replacing the need for power-use for heating
   * the ubiquitous availability of Internet connectivity allows for "smart" applications, saving power-use
(one can also say that ubiquitous availability of Internet connectivity makes that the fossil fuel industry has become more efficient)


## now I go off on a tangent
### thought experiment:
What if consumers had access to 2 Internets: 1 that is expensive, always on, always consuming energy. And another one, that is optimised for least energy consumption. The least energy-Internet could be solar/wind powered, and for workloads where you don't care about them finished 'right now'. For instance downloading movies, making backups


## protocols:
Tussle between security and resource use: we want the internet to be more secure, and we tack on technology ( HTTP->HTTPS , DNSSEC , RPKI , BGPSEC ) that will typically cause more packets and/or more resource use at the end-points (clients/servers). To what extent is a secure Internet less sustainable. Doing security in layers is extra costly (lower layers encrypt traffic that is already encrypted, causing double work, which adds a little security, at the expense of a lot of resource use?)

## references:
ICT energy use in China:
https://www.sciencedirect.com/science/article/pii/S0140988319301288
Greenpeace click clean (2017):
https://www.greenpeace.org/usa/fighting-climate-chaos/click-clean/ 
