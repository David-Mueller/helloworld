# Einladung


``` scala
val evening = new Event(
  name -> "Hockete bei Susi && David"
  start -> Date.fromString("21.07.2017"),
  end -> Infinity,
  place -> new House((Susi,David), "Ulm") // = CompletableFuture<Address>
);

val invitations = Partycrew.toList.map(Objects.inviteTo(_, evening)).parallelStream();

invitations
  .sendAll( force -> true, replyto -> (David.email, David.whatsApp) )
  .then( responses => {
    if ( responses.contains("no") or responses.contains("keine Zeit") ) {
      while (true) { World.run("0 / 0"); }
    } else {
      Susi.setProperty("Spendierhosen", "on");
      David.buyAllTheThings( food -> true, drinks -> true );
      return David.providePlatzZumUebernachten( maxCount -> 12 );
    }
  });
```
