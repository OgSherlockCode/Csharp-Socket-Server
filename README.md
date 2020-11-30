# Csharp-Socket-Server
This socket server receives packets regardless of their size.

use:
```
class Program
    {
        static NetworkComponent server = new NetworkComponent();
        static void Main(string[] args)
        {
            server.Connected += new EventHandler<Socket>(Connect);
            server.StartServer("127.0.0.1", 5000, ProtocolType.Tcp);
        }

        private static void Connect(object sender, Socket e)
        {
            byte[] buf = server.Recive(e);
            Console.WriteLine(Encoding.ASCII.GetString(buf, 0, buf.Length));
        }
    }
```
