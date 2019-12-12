## Access Modifier
| Modifier | Same class | Same package | Subclass | Any Class |
|:--------:|:----------:|:------------:|:--------:|:---------:|
|  public  |      Y     |       Y      |     Y    |     Y     |
|  private |      Y     |       Y      |     Y    |     N     |
|  public  |      Y     |       Y      |     N    |     N     |
|  default |      Y     |       N      |     N    |     N     |

|Symbol|Description|
|:--------------:|:----------:|
| + | public |
| - | private |
| # | protected |
| AbstractClass* | abstract |
| <\<Interface>> | interface |
| <–– | extends |
| <-- | implements |
| ◇–– | composite |
| method()* | abstract |
| final | final |
| static | static |

## GUI
```java
JPanel panel = new JPanel(new GridLayout(3, 2));
panel.getComponents();
panel.setBorder(BorderFactory.createEmptyBorder(8, 8, 8, 8));
this.setDefaultCloseOperation(JFrame.DO_NOTHING_ON_CLOSE);
HIDE_ON_CLOSE / DISPOSE_ON_CLOSE / EXIT_ON_CLOSE
this.setLocationByPlatform(true);
this.getContentPane();
```
## Event Handling
```java
class SampleEvent implements ActionListener {
    public sampleEvent() {
        button.addActionListener(this);
    }
    public void actionPerformed(ActionEvent ae) {
        if(ae.getSource().equals(btn)) { }
    }
}
```
```java
button.addActionListener((ActionEvent ae) -> { });
```
---
```java
label.addMouseListener(new MouseListener() {
    public void mouseClicked(MouseEvent me) { }
    public void mousePressed(MouseEvent me) { }
    public void mouseReleased(MouseEvent me) { }
    public void mouseEntered(MouseEvent me) { }
    public void mouseExited(MouseEvent me) { }
});
```
```java
label.addMouseListener(new MouseAdapter() {
    public void mouseClicked(MouseEvent me) { }
});
```
---
```java
this.addWindowListener(new WindowAdapter() {
    public void windowActivated(WindowEvent e) { }
    public void windowClosed(WindowEvent e) { }
    public void windowClosing(WindowEvent e) { }
    public void windowDeactivated(WindowEvent e) { }
    public void windowGainedFocus(WindowEvent e) { }
    public void windowLostFocus(WindowEvent e) { }
    public void windowOpened(WindowEvent e) { }
    public void windowStateChanged(WindowEvent e) { }
});
```

## Array / Collections
```java
String[] string_array = new String[10];
string_array[0] = "First";
```
```java
HashMap<String, Integer> map = new HashMap<>();
map.put("age", 10);
map.get("age");
map.remove("age");
map.clear();
```
```java
ArrayList<String> string_list = new ArrayList<>();
string_list.add("hello");
string_list.get(0);
string_list.size();
string_list.indexOf("hello");
string_list.remove("hello");
string_list.remove(0);
string_list.clear();
```
## Thread
```java
class SampleThread implements Runnable {
    public void run() { Thread.sleep(1000); }
}
```
```java
Thread t = new Thread(new SampleThread());
t.start();
```
---
```java
public synchronized void notifyme(){ this.notify(); }
public synchronized void run() { this.wait(); }
```

## I/O
```java
File f = new File("data.dat");
if (f.exists()) {
    FileInputStream fin = new FileInputStream(f);
    ObjectInputStream oin = new ObjectInputStream(fin);
    out_obj = oin.readObject();
    fin.close(); oin.close();
}
```
```java
FileOutputStream fout = new FileOutputStream("data.dat");
ObjectOutputStream oout = new ObjectOutputStream(fout);
oout.writeObject(...);
fout.close(); oout.close();
```
---
```java
DataInputStream din = new DataInputStream(fin);
din.readDouble(); din.readBoolean();
din.readByte(); din.readChar();
din.readDouble(); din.readFloat();
din.readInt(); din.readLong();
din.readShort(); din.readUnsignedByte();
din.readUnsignedShort(); din.readUTF();
```

## Others
```java
for(int i: int_array) { }
```