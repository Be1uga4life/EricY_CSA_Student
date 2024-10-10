---

---

```java
import java.util.HashMap;
import java.lang.Math;
import java.util.Random;

public class Distance {
    @FunctionalInterface
    interface DistanceCalculation {
        double findDistance(int x1, int y1, int x2, int y2);
    }

    public static void main(String[] args) {
        Random rand = new Random();
        HashMap<int[], int[]> coordinates = new HashMap<int[], int[]>();
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 10; j++) {
                int[] a = {i + rand.nextInt(10), j + rand.nextInt(10)};
                int[] b = {i + rand.nextInt(10), j + rand.nextInt(10)};
                coordinates.put(a, b);
            }
        }
        DistanceCalculation calculation = (x1, y1, x2, y2) -> {
            double ans;
            double xChunk = (x1 - x2)*(x1 - x2);
            double yChunk = (y1 - y2)*(y1 - y2);
            ans = Math.sqrt(xChunk + yChunk);
            return ans;
        };
        for (int[] coord1 : coordinates.keySet()) {
            int[] coord2 = coordinates.get(coord1);
            int x1 = coord1[0]; int y1 = coord1[1];
            int x2 = coord2[0]; int y2 = coord2[1];
            System.out.println(calculation.findDistance(x1, y1, x2, y2));
        }
    }
}
```


```java
class Emoji {
    private String symbol;
    private String name;

    public Emoji(String symbol, String name) {
        this.symbol = symbol;
        this.name = name;
    }

    public String getSymbol() {
        return symbol;
    }

    public String getName() {
        return name;
    }

    public void displayEmoji() {
        System.out.println("Emoji: " + symbol + " - " + name);
    }
}

class EmojiCollection {
    private Emoji[] emojis;
    private int count = 0;

    public EmojiCollection(int size) {
        emojis = new Emoji[size];
    }

    public void addEmoji(Emoji emoji) {
        if (count < emojis.length) {
            emojis[count] = emoji;
            count++;
        } else {
            System.out.println("Collection is full!");
        }
    }

    public void displayAllEmojis() {
        for (int i = 0; i < count; i++) {
            emojis[i].displayEmoji();
        }
    }
}

public class EmojiDemo {
    public static void main(String[] args) {

        Emoji smiley = new Emoji("😊", "Smiley Face");
        Emoji heart = new Emoji("❤️", "Heart");
        Emoji thumbsUp = new Emoji("👍", "Thumbs Up");
        EmojiCollection collection = new EmojiCollection(5);
        collection.addEmoji(smiley);
        collection.addEmoji(heart);
        collection.addEmoji(thumbsUp);
        collection.displayAllEmojis();
    }
}
EmojiDemo.main(new String[0]);
```

    Emoji: 😊 - Smiley Face
    Emoji: ❤️ - Heart
    Emoji: 👍 - Thumbs Up

