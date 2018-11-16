# Ejericico 3.

###Realizar una app en express (o el lenguaje y marco elegido) que incluya variables como en el caso anterior.

Se crea una aplicación en el framerwork Springboot de java, el siguiente codigo muestra las variables en los controladores del programa.

~~~
@RestController
@RequestMapping("api/v1/naufragio")
public class NaufragioController {


    private final NaufragioMock naufragioMock;

    public NaufragioController(NaufragioMock naufragioMock) {
        this.naufragioMock = naufragioMock;
    }

    @GetMapping
    public List<Naufragio> get() {
        return naufragioMock.get();
    }

    @GetMapping("{id}")
    public Naufragio get(@PathVariable Long id){
        return naufragioMock.getById(id);
    }

    @PostMapping
    public  Naufragio create(@RequestBody Naufragio naufragio)
    {
        return naufragioMock.create(naufragio);
    }

    @PutMapping("{id}")
    public Naufragio update(@PathVariable Long id, @RequestBody Naufragio naufragio){
        return naufragioMock.update(id, naufragio);
    }


    @DeleteMapping
    public Naufragio delete(@PathVariable Long id){
        return naufragioMock.delete(id);
    }
}

~~~
