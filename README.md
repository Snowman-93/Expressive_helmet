# An Expressive Helmet

Building AI course project

## Summary

This helmet could sense its wearer’s facial expressions - mouth muscle movements as well eye and eyelid movements. The outer shell of the helmet would react accordingly. For example, the helmet would express a smile with LED lights when a head inside it smiled as well, or blink when the head blinked.

## Background

The idea would help shy people interact better publicly without having to resort to expressionless masks. Plenty of reclusive people tend to wear masks to cope with their social limitations, but they cannot express themselves facially in public. This kind of issue would be mitigated if an AI method for detecting facial expressions could be applied to facial coverings like masks or helmets. My own personal motivation is to use this kind of technology to entertain people in appropriate places where costumes are permitted, like in nightclubs. I remember people having been amazed at the unforeseen sound sensitive T-shirt which was bought from London and which I wore. They most definitely would be even more amazed should they witness this in the flesh (more accurately, in the mechanics). Also, this could be used for creating your own alter ego. For some, it is very refreshing to be somebody else for a change – just ask the contestants of Masked Singer competitions!

## Data and AI techniques

The data source for my project would be the movement detection and the current position of a mouth. Maybe in a more developed sense, using this kind of data for test sets and training sets could prove beneficial. Currently I see the most benefit in conditional functions, like certain numbers coming at certain intervals, which should be demonstrated in the exemplary code. Perhaps this could be applied to the sense of different mouth positions.

## How is it used?

My current vision would be that a camera/cameras be attached to the certain part(s) of the helmet so they can recognize certain positions of the mouth and eyes. In other words, it would use facial movement recognition technology. The helmet would either have wide enough hole for the whole head to go in or an opening and closing mechanism, like in some wallets. If the inside of the helmet is too hot, maybe there could be some minor air conditioners. I can imagine it being attractive to those who want to protect their privacies, those who wish to play as another character and those who wish to entertain people.

Here are the pictures of one version of the helmet I envisioned, made by me. It is part of an imaginary costume I christened "Blueberry". On the other hand, neck pains should be avoided.

![Blueberry_sketch](/Blueberry_sketch.jpg)

![Blueberry_wink](/Blueberry_wink.png)

![Blueberry](/Blueberry.png)

The exemplary code:

    def generate():
        # this function generates 800 random zeros and ones

        # this is meant to simulate the time period where a human has occasionally neutral and smiling
        # expressions, represented by zeroes and ones. We also assume that the wider the mouth movement,
        # the longer the rows of 1 and shorter intervals between them and zeroes
        neutral = 0
        wider = 1
        seq = np.random.choice([neutral,wider], p=[0.5, 0.5], size=800)
        return seq

    def count(seq):
        # this function returns the number of occurrences of 111 in the sequence
        count = 0
        for i in range (len(seq)-4):
            if int(seq[i]) == 1 and int(seq[i+1]) == 1 and int(seq[i+2]):
                count += 1
        return count

    def smile():
        # if enough occurrences of 111 happened in the count function, the function returns the value "true"
        seq = generate()
        smile_count = count(seq)
        if smile_count < 100:
            return False
        return True

    def main():
        # if the smile function returned "true", the smile would occur, and if not, the neutral expression would occur instead 
        if smile():
            print("Let's put a smile on that face!")
        else:
            print("Neutral expression.")

    for i in range(10):
        main()

## Challenges

Because this project is currently 99.999% hypothetical and I didn’t have time to investigate further in it yet, I cannot say for sure what kind of limitations it would have. I think my biggest challenges would be connecting facial recognition technology to the LED technology. My current assumption is that it can be done with programming, but I have to search the right libraries for it, and I don’t know where they are or if they even exist. This project also potentially cannot solve the conditioner problem, depending on the space of the helmet. As for the ethical notes, this project has a risk of actually making some people even more shy to show their true faces instead of easing their publicity anxiety.

## What next?

This project could grow even more advanced and impressive by adding the ability to sense rapid facial movements in different positions. For example, the expressive mask/helmet could be “smiling” while talking at the same time if the face inside the helmet does the same.

However, if I am to advance in this project, I have to take further research into the building materials and facial recognition system. I am also quite convinced I might need some assistance from those who have looked into these more than I before I can come up to right conclusions even further.

## Acknowledgements

The exemplary code is based on the advanced level of exercise 7, “Flip the coin”, which is part of Elements of AI: Building AI online course. The code is used with explicit permission from the course creators University of Helsinki and Reaktor. My sources of inspiration for this project are Hatsune Miku, Daft Punk, Deadmau5 and Japanese technology along with its kawaii culture. I also want to give credit to my family for the idea of a facial recognition system.
