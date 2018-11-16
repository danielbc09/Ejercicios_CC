# Ejericico 4.

### Crear pruebas para las diferentes rutas de la aplicación.

Para la aplicación anterior se crean los siguientes test unitarios, de las rutas del controlador.

~~~
 @Mock
    private NaufragioMock naufragioMock;


    @InjectMocks
    NaufragioController naufragioController;

    private MockMvc mockMvc;

    @Before
    public void setUp() {
        MockitoAnnotations.initMocks(this);
        mockMvc = MockMvcBuilders.standaloneSetup(naufragioController)
                .build();
    }

    @Test
    public void getNaufragio() throws Exception {

        Naufragio naufragio1 = new Naufragio();
        naufragio1.setId(1l);
        naufragio1.setNombre("Naufragio1 Test");
        naufragio1.setAnoDescubrimiento(1999);
        naufragio1.setDescripcion("Naufragio de prueba 1");

        Naufragio naufragio2 = new Naufragio();
        naufragio1.setId(2l);
        naufragio1.setNombre("Naufragio2 Test");
        naufragio1.setAnoDescubrimiento(1999);
        naufragio1.setDescripcion("Naufragio de prueba 2");


        when(naufragioMock.get()).thenReturn(Arrays.asList(naufragio1, naufragio2));

        mockMvc.perform(get("/api/v1/naufragio/"))
                .andExpect(status().isOk());
    }

    @Test
    public void getById() throws Exception {

        Naufragio naufragio1 = new Naufragio();
        naufragio1.setId(1l);
        naufragio1.setNombre("Naufragio1 Test");
        naufragio1.setAnoDescubrimiento(1999);
        naufragio1.setDescripcion("Naufragio de prueba 1");

        when(naufragioMock.getById(1l)).thenReturn(naufragio1);

        //When
        mockMvc.perform(get("/api/v1/naufragio/1")
                .contentType(MediaType.APPLICATION_JSON))
                .andExpect(status().isBadRequest())
                .andExpect(jsonPath("$.nombre", equalTo(naufragio1.getNombre())));
    }
~~~
