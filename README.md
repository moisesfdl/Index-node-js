# Index-node-js
localhost

const express = require("express");
const app = express();
const BodyParser = require("body-parser");
const connection = require("./DataBase/database");
const metadadoscorrecoe = require("./DataBase/MensagemEletronica.js");
const financeiro = require("./DataBase/financeiro.js");
const BancoItau = require("./DataBase/BancoItau.js");
const ReceitaFederalBrasileira = require("./DataBase/ReceitaFederalBrasileira.js");
const CorretoraAdvfn = require("./DataBase/CorretoraAdvfn.js");
//connection2 = require("./DataBase/database2.js");
const NotaFiscal = require("./DataBase/contribuinte.js");
const ComprasOnline = require("./DataBase/LojasAmericanas.js");
const Beneficiario = require("./DataBase/mastercard.js");
const CreditoOnlines = require("./DataBase/CreditoOnline.js");
const PlayStoreMicrosoft = require("./DataBase/PlayStoreMicrosoft.js");
const BancoDoBrasil = require("./DataBase/BancoDoBrasil.js");
const PontoAcumulado = require("./DataBase/livelo.js");
const Celular = require("./DataBase/vivo.js");
const FolhaSalario = require("./DataBase/MinisterioTrabalhoBrasileiro.js");
const FontePagadora = require("./DataBase/PremiosOnline.js");
const BitCoin = require("./DataBase/CommissionEuropeia.js");
const CambioMoeda = require("./DataBase/CambioMoeda.js");
const BeneficioBNDES = require("./DataBase/BNDES.js");
const BankInternacional = require("./DataBase/BankInternacional.js");


connection
    .authenticate()
    .then(()=>{
    console.log("DB conectado")
})
    .catch((msgErr)=>{
    console.log(msgErr);
});
/*connection2
    .authenticate()
    .then(()=>{
        console.log("DataBase conectada")
    })
        .catch((msgErr)=>{
            console.log(msgErr);
        });*/

/*app.get("/models/mod_ocorrencia/ocorrencia1/informeOcorrencia.js", (req, res)=>{
    var info = info;
    res.render("home/index.ejs", {
        info: info
    })
})*/
app.set(`view engine`, `ejs`);
//app.set('DataBase engine', 'sql');
app.use(express.static('public'));
//app.use(sequelize('.sql'));
app.use(BodyParser.urlencoded({extended: false}));
app.use(BodyParser.json());
//app.use(express.application('DataBase/database.js'));
app.get("/", (req, res)=>{
    res.render("home/index.ejs");
})

app.get("/InformePessoal", (req, res)=>{
 const Empresa = "MetaDados&Correçoes";
   const TitularLegal = req.params.TitularLegal;
   const msgEmpresa = true;

   const InformacaoPessoals = [
    {TitularLegal: "Moises ferreira de lima", ctpe:"Carteira Trabalho Profissional Executiva", ctpeNumero: "77646",
        ctpeSerie: "0150", RG: "27.950.938-8", CPF: "275.551.158-32", CNPJ: "35.669.326/0001-90", 
        Atuacao: "Assessoria Juridica Propriamente dito sem socio, \n"
        +"de gestao empresarial executivo \n"
        +"de gestao financeira de ganhos pela fonte pagadora do extrangeiro \n"
        +"por premiaçao online, \n"
        +"de limitaçao de atos de tramitaçao de direito atipico sobre direito \n"
        +"reservado a Moises ferreira de lima, por açao de atos de contra disposto\n",
        NIS: "125.41632.83-7", TituloEleitoral: "239832530116", Passaport: "GD743426",
        email: "moisesfdl_pbt@hotmail.com.br", email2:"moisesprobabilidade@gmail.com",
        celular: "5512996497466", logInUserOnline: "moisesfdl"
    }
   ];
  // metadadoscorrecoe.findAll({raw: true}).then(metadadoscorrecoes =>{
       //console.log(metadadoscorrecoes);
       res.render("home/InformePessoal.ejs", {
        //metadadoscorrecoes: metadadoscorrecoes,
        metadadoscorrecoe: metadadoscorrecoe,
        Empresa: Empresa,
        TitularLegal: TitularLegal,
        InformacaoPessoals: InformacaoPessoals,
        Mensage: msgEmpresa
      });
    //});
});
app.get("/interactive_brokers", (req, res)=>{
    const Investir = req.params.Investir;
    const correcaos = [
        {Investir:"tws", beneficiario:"Moises ferreira de lima", commission:"!", AccountID:"!",
            CPF:"275.551.158-32", email:"moisesfdl_pbt@hotmail.com.br", email2:"moisesprobabilidade@gmail.com",
            CNPJ:"35.669.326/0001-90",Passaport:"GD743426",RG:"27.950.938-8", UF:"BRASIL"
        }
    ]
    const FundoCapitals = [
        {Beneficiario:"Moises ferreira de lima", NetLiquidValid:2700000.00, BuyngPower:12000000.00,
            Operando:"Negativo", CPF:true, email:true, email2:true, CNPJ:true, Passaport:true
        }
    ]
    res.render("investidor/interactive_brokers.ejs", {
        Investir: Investir,
        correcaos: correcaos,
        FundoCapitals: FundoCapitals
    });
})
app.get("/financeiro", (req, res)=>{
    var beneficiario = beneficiario;
    var titular = "Moises ferreira de lima";
    var cpf = "275.551.158-32";
    var cnpj = "35.669.326/0001-90";
    var email = "moisesfdl_pbt@hotmail.com.br";
    var valor = valor;
    var InformPag = true;
    var beneficio = beneficio;
    var pays = [
        {beneficiario: "lojas-americanas", preco: 20*0},
        {beneficiario: "Original Veiculo", valorPag: 221700.00*0, datCompra: "10/10/2023", 
            titular: "Moises ferreira de lima", CPF: "275.551.158-32", CobInternacional: "MasterCard",
            modeloAuto: "Taos Hegline 2023",  situacao: "aguardando entrega ate o momento"
        },
        {Beneficiario:"Moises ferreira de lima", boleto:"30190.00003  01641.330004  55678.462049  7  97940000013990",
            Beneficio:"MasterCard", email:"moisesfdl_pbt@hotmail.com.br", Authenticator:"88042E6831E2955D66F25C696C1114BFCB0E4D86",
            LotteryMicrosoft:true, PagamentoOnline:139*0, CreditoOnline:true,MasterCard:true,
            cpf:"275.551.158-32", pagamentoEfetuado:true, pedido:"02-1031508993"
        } 
    ];
    var deposits = [
        {beneficio: "MasterCard", data: "26/07/2024", beneficiario: "banco-itau", valor: 250*0},
        {Beneficiario:true, client:"Moises ferreira de lima",  valor_deposit:2500*0,ContaBancaria:true,CPF:"275.551.158-32", data_deposit:"29/07/2024"}
    ];
    var TransPixs = [
        {beneficiario:true,BeneficiarioPix: "Dina Chagas Araujo", CPF:"09180615805", valor:1000.00, data:"28/07/2024", agendado:"29/07/2024",
            ref:"pra dona dina receber e me repassar um retorno de R$500"
        }
    ];
    VivoCelulars = [
        {celular:"5512996497466",CPF:"27555115832",CNPJ:"35669326000190",
            email:"moisesfdl_pbt@Hotmail.com.br",credito:0.001*60*60*12*30/1
        }
    ];
    cartorios = [
        {revogacao:"Certidao Nascimento", CPF:"27555115832",CNPJ:"35669326000190",
            email:"moisesfdl_pbt@Hotmail.com.br",PagamentoRevogacao:0.001*60*60*12*30/1    
        }
    ],
    FolhaSalarios=[
        {CTPE:"Carteira Trabalho Profissional Executivo",CtpeNumero:"77646",CtpeSerie:"0150",
            EmpresaPagadora:"moises ferreira de lima 27555115832",NomeFantasia:"MetaDados&Correçoes",
            Funcao:"Diretor Geral Executivo",CNPJ:"35669326000190",CPF:"27555115832",RG:"279509388",
            Salario:0.006*60*60*12*30/1,banco:"Banco Itau", agencia:"1760",conta:"10347-1", DiaPagamento:5
        }
    ],
    LucroCripto= [
        {Beneficiario:"Moises ferreira de lima",CPF:"27555115832",CNPJ:"35669326000190",
            email:"moisesfdl_pbt@hotmail.com.br",email2:"moisesprobabilidade@gmail.com",Vol:true,Golemcoin:true,
            stakcoin:true,peidcoin:true,rend_bancaria:1000.0,rend_bancaria_por_mes:true,dia:5,BancoItau:true
        }
    ]
    LucroBRL = [
        {beneficiario:"Moises ferreira de lima",PessoaFisica:true, PessoaJuridica:true,CPF:"275.551.158-05",
            email:"moisesfdl_pbt@hotamil.com.br",email2:"moisesprobabilidade@gmail.com",CNPJ:"35669326000190",
            remessaonline:true,BancoItau:true,Passaport:true
        }
    ]
    CreditoPessoal = [
        {Benefiario:"Moises ferreira de lima",CPF:"27555115832",CNPJ:"35669326000190",email:"moisesfdl_pbt@hotmail.com.br",
            email2:"moisesprobabilidade@gmail.com",celular:"12996497466",BNDES:true,ValordCreditoBNDES:true
        }
    ]
    CreditoBNDES = [
        {Beneficiario:"Moises ferreira de lima",CPF:"27555115832",CNPJ:"35669326000190", email:"moisesfdl_pbt@hotmail.com.br",
            email2:"moisesprobabilidade@gmail.com",BNDES:true,ValorBeneficioBNDES:true,TituloEleitoral:"239832530116",
            NIS:"12541632837",Passaport:"GD743426"
        }
    ]
    res.render("financeiro/financeiro", {
        CambioMoeda: CambioMoeda,
        CreditoPessoal: CreditoPessoal,
        LucroBRL: LucroBRL,
        BitCoin: BitCoin,
        LucroCripto: LucroCripto,
        FontePagadora: FontePagadora,
        FolhaSalario: FolhaSalario,
        FolhaSalarios: FolhaSalarios,
        CreditoOnlines: CreditoOnlines,
        financeiro: financeiro,
        titular: titular,
        beneficio: beneficio,
        VivoCelulars: VivoCelulars,
        CreditoBNDES: CreditoBNDES,
        Celular: Celular,
        cpf: cpf,
        cnpj: cnpj,
        beneficiario: beneficiario,
        BeneficioBNDES: BeneficioBNDES,
        valor: valor,
        pays: pays,
        deposits: deposits,
        TransPixs: TransPixs,
        email: email,
        cond: InformPag
     });
});
app.get("/Empreendedor", (req, res)=>{
    res.render("projetos/Empreendedor.ejs");
});
app.get("/advfn", (req, res)=>{
    const titular = req.params.titular;
    const investimentos = req.params.investimentos;

    const Investidors = [
        {Investidor:"Moises ferreira de lima", portifolio:"moisesfdl", email:"moisesfdl_pbt@hotmail.com.br", cpf:"275.551.158-32",
            email2:"moisesprobabilidade@gmail.com", cnpj:"35.669.326/0001-90",passaport:"GD743426",celular:"5512996497466",
            SaldoCaixa:87575208.29,CustoPortifolio:4627738.76,CustoRendimento:1061791.46, porcento:22.94,SaldoLucroRealizado:59190947.05, CursoCorretor:true,ConcessaoSusep:true
        }
    ]
    const RetiradaValors = [
        {beneficiario:"Moises ferreira de lima", cpf:"275.551.158-32", email:"moisesfdl_pbt@hotmail.com.br",
            ContaPessoaFisica:true, Banco:"Banco Itau", agencia:"1760", conta:"10347-1", ValorCreditoConta:1000000.00,
            DataCredito:"31/07/2024", Localizacao:"SJC/SP/Brasil"
        },
        {Pagamento:"Concessao Especial",IRPF:"IRPF2023",CPF:"275.551.158-32",ValorPagConcessao:3000000.00*0,
            PessoaFisica:true
        },
        {Pagamento:"Compra-Automovel",Beneficiario:"Original Veiculo",CNPJ_Beneficiario:"60.894.136/0004-67",
            CPF:"275.551.158-32",ValorPagamento:221700.00*0, CondicaoPagamento:"Invoice"
        }

    ]
    res.render("investidor/advfn.ejs", {
        CorretoraAdvfn: CorretoraAdvfn,
        titular: titular,
        Investidors: Investidors,
        RetiradaValors: RetiradaValors,
        investimentos: investimentos
    });
})
app.get("/bankofamerica", (req, res)=>{
    const beneficiario = req.params.beneficiario;
    //#beneficiario == {titular : beneficiario2}
    const TitularBeneficios = [
        {beneficiario: "Moises ferreira de lima", email: "moisesfdl_pbt@hotmail.com.br", cpf: "275.551.158-32",
            cnpj: "35.669.326/0001-90", email2:"moisesprobabilidade@gmail.com", passaport: "GD743426",
            celular: "5512996497466", residente: "Brasileiro"
        },
        {beneficiario: "Moises ferreira de lima", email: "moisesfdl_pbt@hotmail.com.br", passaport: "GD743426",
            SolicitacaoCompraImovel: "Solicitaçao de compra de imovel", Pais: "Estados Unidos", Cidade: "Pensylvania",
            ValorImovel: 2000000.00, DescRecurs:"Autorizo Descontar Recurso",  AssinaturaEletronica: "Moises ferreira de lima",
            CartorioLocal: "Registro Eletronico Digital Online em meu nome do imovel\n"+"e me notificar queando tiver pronto", 
        }
    ];
    const msgCertificadoRecursoFinanceiro = true;
    res.render("BankInternacional/bankofamerica.ejs", {
        beneficiario: beneficiario,
        TitularBeneficios: TitularBeneficios,
        MensagemEletronicaOnline: msgCertificadoRecursoFinanceiro
    });
});
app.get("/SetorJuridico", (req, res)=>{
    const advogados = req.params.advogados;
    const ProcessDigitals = [
        {advogados:"Advogados", Process:"Analize de cartorio", ValorProcess:15000,
            AtoProcess:"Fiduciario", Ref:"se caso formalizou pagamento \n"
            +"solicitar a entrega das chaves e o documento e o registro em cartorio", CPF:"27555115832",
            CNPJ:"35.669.326/0001-90", EMAIL:"moisesfdl_pbt@hotmail.com.br"
        },
        { advogados:true,process:"Banco do brasil",ValorProcess:2000,AtoProcess:"Devoluçao Oferta Publica",
            Ref:"em 2019 , eu efetuei uma oferta publica , e ao cair o valor na conta , saldo liquido \n"
            +"em um milhao de reais , as 09:00 hora o gerente me liga , subjulgando o valor e como eu \n"
            +"teria conseguido tal valor e por que eu tinha carencia de uma ano pra saldar a primeira parcela \n"
            +"e apos essa afirmaçao , o gerente me informa que iria cancelar , mas na verdade \n"
            +" ele estornou o valor , assim ficou na tela da conta , e agora em 2024 , mes 10032024 \n"
            +"o banco me acionou uma ordem administrativa por que ainda consta o saldo no sistema \n"
            +"da conta , e pelo ato sucursal de ususpaçao de direito atipico me disvirtuou de titula da conta \n"
            +"e a administraçao do banco esta suspeito de atentarem contra minha pessoa e alienar o ben economico \n"
            +"me mandaram assina pra encerrar conta , e nao querem devolver o valor \n", CPF:"275.551.158-32",
            CNPJ:"35.669.326/0001-90",EMAIL:"moisesfdl_pbt@Hotmail.com.br"
        }
    ]
    res.render("OAB/SetorJuridico.ejs", {
        advogados: advogados,
       ProcessDigitals: ProcessDigitals
    });
});
app.get("/bradesco", (req, res)=>{
    var Reclamacao = req.params.Reclamacao;
    const Cobrancas = [
        {Reclamacao:"Premio Bruto Titulo de Capitalizaçao", Sucursal:false, ato: "0794", apolice:"00002550",
            certificado:"000053481", ValorPremio:200000.00, PeriodoVigencia:false, cessionario:"Moises ferreira de lima",
            cedente:"bradesco", ProcessoSusep:"15414100463/2009-22", CNPJ:"33010851/0001-74"
        },
        {Banco:"Banco Itau", agencia:"1760",conta:"10347-1",CNPJ:" 60.872.504/0001-23",beneficiario:"Moises ferreira de lima",CPF:"275.551.158-32",
            ValorPremio:true,Reclamacao:true,ValorCredito:200000.0*0
        }
    ]
    res.render("DadosBancario/bradesco.ejs", {
        Reclamacao: Reclamacao,
        Cobrancas: Cobrancas
    });
})
app.get("/BancoItau", (req, res)=>{
    const ContaBancaria = req.params.ContaBancaria;
    const LimitCredits = req.params.LimitCredits;
    const IRPF = req.params.IRPF;
    const UncConta = true;
    const DadosBancarios = [
        {ContaBancaria: "Banco-Itau", agencia: "1760", conta: "10347-1", Titular: "Moises ferreira de lima",
            CPF: "275.551.158-32", CNPJ: "35.669.326/0001-90", email:"moisesfdl_pbt@hotmail.com.br", 
            email2:"moisesprobabilidade@gmail.com", celular:"5512996497466", passaport: "GD743426",
            TituloEleitoral:"239832530116"
        },
        {IRPF:"IRPF-2019", valorReceber:200000.00, situacao:"aguardando credito em conta", PessoaFisica:true,
            CPF:"275.551.158-32", creditoConta:true,
        },
        {Premio:"Lottery Microsoft", Beneficio:"MasterCard", DataAprovaçaoBeneficio:"01/01/2024", 
            EmailPremiado: "moisesfdl_pbt@hotmail.com.br", CPF:"275.551.158-32", Situacao:"aguardando o banco itau"
        +"entregar cartao de credito , e liberar meus"+" pagamentos de DDA garantidos dos agendados"},
        {IRPF:true, Irpf2020:"IRPF-2020", valorReceber2:300000.00, situacao2:"aguardando credito em conta", PessoaFisica:true,
            CPF:"275.551.158-32", creditoConta:true,
        },
        {LimitCredits:true, Titular:true, ContaBancaria:true, agencia:true, conta:true, LimiteDDA: 10000.00,Diary: true, 
            LimitPIX: 70000.00, LimitCreditsSaque:true,MaxSaque: 6500.00,MinSaque:1500.00, FolhaCheq:true,
            CartaoCredito:"cartao Credito MasterCard", CartaoDebit: "Cartao Debit MasterCard", BeneficioCardCredit:7500.00,
            BeneficioCardDebit: 2500.00, MasterCard:true,LotteryMicrosoft:true,SituacaoCreditPreAprovado:"Aguardando o banco entregar\n"
            +"cartao credito com beneficio MasterCard",
         },
         {beneficio:"Moises ferreira de lima", CobrancaPix:"00020126570014BR.GOV.BCB.PIX0111275551158320220beneficio mastercard52040000530398654072500.005802BR5923MOISES FERREIRA DE LIMA6015SAO JOSE DOS CA622605225R68KV5PaxuCjJihICTZWx6304D2AF",
            cpf:"275.551.158-32", email:"moisesfdl_pbt@hotmail.com.br", data:"29/07/2024"
         }
    ];
       Beneficios = [
            {beneficio:"MasterCard",CPF:"27555115832",CNPJ:"35669326000190",email:"moisesfdl_pbt@hotmail.com.br",
                BeneficioDebit:0.01*60*60*12/12,cedente:true,cessionario:true,MasterCard:true,LotteryMicrosoft:true
            }
        ]
    res.render("DadosBancario/BancoItau.ejs", {
        BancoItau: BancoItau,
        ContaBancaria: ContaBancaria,
        LimitCredits: LimitCredits,
        IRPF: IRPF,
        DadosBancarios: DadosBancarios,
        Unica: UncConta
    });
})
app.get("/invoice", (req, res)=>{
    const titular = "Moises ferrira de lima";
    const email = "moisesfdl_pbt@hotmail.com.br";
    const CPF = "275.551.158-32";
    const CNPJ = "35.669.326/0001-90";
    const Beneficiario = req.params.Beneficiario;
    const CondPays = [
        {Beneficiario: "Dina Chagas Araujo", cpf: "091.806.158-05", valorPagInv: 200000.00*0},
        {Beneficiario: "Fernando (Vizinho) ", valorPagInv: 500000.00*0, Motivo:"depois de uma pergunta se tinha alguem querendo comprar \n"
            +"faço atravez desta condiçao de pagamento minha oferta"
        },
        {Beneficiario:"Original Veiculos", valorPagInv: 221700.00*0, CNPJ_Beneficiario:"60.894.136/0004-67"},
        {Beneficiario: "Zap-Imoveis", valorPagInv: 2500000.00*0, CNPJ_Beneficiario: "04.060.842/0001-90" , ResComercial: "Jardim Industrias"},
        {beneficiario:true,beneficiario2:"Banco Real", Pagamento_online:2000*0,CPF:"275.551.158-32", data:"01/02/2024",RefPag:"emprestimo 2008"},
        {beneficiario:true,beneficiario3:"lojao bras", CNPJ_Beneficiario3:"71.831.721/0001-91", Pagamento_online2:150*0, CPF:"275.551.158-32", dataPagamento:"29/02/2024", refPag3:"compra"}
    ];
    res.render("PayInvoice/invoice.ejs", {
        titular: titular,
        Beneficiario: Beneficiario,
        CPF: CPF,
        email: email,
        CNPJ: CNPJ,
        CondPays: CondPays
    });
});
app.get("/rfb", (req, res)=>{
    const Notific = "Restituiçao a receber";
    const irpf2019 = req.params.irpf2019;
    const irpf2020 = req.params.irpf2020;
    const titular = req.params.titular;
    const ConcessaoEspecial = req.params.ConcessaoEspecial;
    const Declaracao = req.params.Declaracao;
    const msgReceitaFederalBrasileira = true;
    const Restituicaos = [
        {irpf2019: "Restituicao IRPF-2019", Cod: "2019/008202866214764", valor: 200000.00, datAprovacao: "14/08/2023"},
        {irpf2020: "Restituicao IRPF-2020", Cod: "2020/183496755202921", valor: 300000.00, datAprovacao: "04/03/2023"},
        {RendaVariavel:"Renda Variavel", CodRecF: "6015", CodProt: "000000001695-AR073857267RW-000000285324", valor: 2500000.00, dataApuracao: "30/07/2021"},
        {restituicao:"IRPF=2019", Pix:"00020126880014BR.GOV.BCB.PIX0111275551158320251restituicao IRPF PRA RECEITA FEDERAL DEPOSITAR 5204000053039865409200000.005802BR5923MOISES FERREIRA DE LIMA6015SAO JOSE DOS CA622605225qNpWrEquqPv5ianiuNGGA63042ED4",
            valor_Pix:200000.00, CPF:"275.551.158-32"
        }
    ];
    const DadosBancarios = [
        {titular: "Moises ferreira de lima", cpf: "275.551.158-32", cnpj: "35.669.326/0001-90", banco: "Banco Itau", agencia: "1760", conta:"10347-1", Motivo: "aguardando receber credito em conta"},
    ];   
    const BensDireitos = [
        {ConcessaoEspecial:"Concessao Especial", Susep:true, Beneficiaria2:"Gisele Fabiana Gomes Oliveira Lima", 
            CPF2:"354.686.228-74", IrpfBeneficio:"IRPF-2023", ValorCredito:2000000.00, CreditoImobiliario:true, PessoaJuridica:true,
            CNPJ:"35.669.326/0001-90", MotivoRef:"Encargos de Pensoes Alimenticia e ajuda financeira pra ela conquistar seu imovel"
        },
        {ConcessaoEspecial:true, ConcessaoEspecial2:"Concessa Especial", Susep:true, beneficiario3:"Dina Chagas Araujno",
            CPF3:"091.806.158-05",IrpfBeneficio2:"IRPF-2023",ValorCredito2:1000000.00,CreditoImobiliario:true, PessoaJuridica:true,
            CNPJ:"35.669.326/0001-90", MotivoRef2:"Saldo de devedor por tempos de ter me ajudado em vida"
        },
        {Declaracao:"Mudança De Genero", IrpfDeclaracao:"IRPF-2024", CPF:"275.551.158-32",
            MotivoRef:"Perseguiçao por ato de ligitimidade e ato de usurpaçao de direito atipico"
            +"e aliciamento por ato de cultismo oriundo e termo aditorio no documento"
            +" de certidao de nascimento , e sou suspeito de ser de outro seio familiar"
            +"europeu de atenas , por isso , estou mudando o meu genero"
            +" assim deus desejou e delegou "
        }
    ]
    res.render("ReceitaFederalBrasileira/rfb.ejs", {
        Beneficiario: Beneficiario,
        ComprasOnline: ComprasOnline,
        NotaFiscal: NotaFiscal,
        ReceitaFederalBrasileira: ReceitaFederalBrasileira,
        Notific: Notific,
        irpf2019: irpf2019,
        irpf2020: irpf2020,
        Restituicaos: Restituicaos,
        ConcessaoEspecial: ConcessaoEspecial,
        titular: titular,
        DadosBancarios: DadosBancarios,
        BensDireitos: BensDireitos,
        Declaracao: Declaracao,
        MensagemEletronica: msgReceitaFederalBrasileira
    });
});
app.get("/premios", (req, res)=>{
    const PremioLotteryMicrosoft = req.params.PremioLotteryMicrosoft;
    const PremioLotteryToyota = req.params.PremioLotteryToyota;
    const msgSorteioLotteryOnline = true;
    const EmailPremiados = [
        {PremioLotteryMicrosoft: "Lottery Microsoft", Beneficiario: "Moises ferreira de lima", email: "moisesfdl_pbt@hotmail.com.br", 
            NumberRef: "M003643XC", SerialNumber:"24512-235665",  BatchNumber: "MSC-142/4120-KTY",  WinningNumbers: "MSN-3982021"},
        {CreditoOnline:true,PremioLotteryToyota:"Lottery Toyota", Beneficiario:true, email:true, celula:"5512996497466", Attached:"713-266-1319",Serial:"902-66"}
    ];
    res.render("PremioOnline/premios.ejs", {
        PremioLotteryMicrosoft: PremioLotteryMicrosoft,
        PremioLotteryToyota: PremioLotteryToyota,
        EmailPremiados: EmailPremiados,
        MensagemEletronicaEmail: msgSorteioLotteryOnline
    });
})
app.get("/cartorio", (req, res)=>{
    var aditamento = req.params.aditamento;
    var Tramites = [
        {aditamento: "Revogaçao ", documento: "Certidao Nascimento", valor: 1000.00, CPF:"275.551.158-32",
            CNPJ: "35.669.326/0001-90", email: "moisesfdl_pbt@hotmail.com.br", motivo: "por motivo de usurpaçao \n"
            +"de direito atipico , eu vou ter que revogar\n"+" a certidao de nascimento , que esta com termo por\n"
            +"carimbo pela Dom Jea Pierry, e Salles, de portugal \n"+"e por isso , vou ter que revoga e solicitar que \n"
            +"seja retirado a autorizaçao , que esta com uma questao\n"+"que o governo federal esta me subjulgando e \n"
            +"nao querem revelar , e talvez minha mamae e outra pessoa", celular: "moisesprobabilidade@gmail.com",
            celular: "5512996497466", passaport: "GD743426"
         },
    ]
    res.render("cartorios/cartorio", {
        aditamento: aditamento,
        Tramites:Tramites
    });
});
app.get("/americanas", (req, res)=>{
    res.render("ComprasOnline/LojasAmericanas/americanas.ejs");
});

app.get("/MensagemEletronica", (req, res)=>{
    res.render("MensagemDireta/MensagemEletronica.ejs");
});
app.get("/bndes", (req, res)=>{
    var Empresa = req.params.Empresa;
    var Beneficio = req.params.Beneficio;

    var BeneficioBNDES = [
        {Beneficiario:"Moises ferreira de lima", CPF:"275.551.158-32",CNPJ:"35.669.326/0001-90",
            email:"moisesfdl_pbt@hotmail.com.br",email2:"moisesprobabilidade@gmail.com",celular:"5512996497466",
            beneficio:true,empreendedor:true,empresa:"moises ferreira de lima 27555115832",RazaoSocial:"MetaDados&Correçoes",
            CondicaoBeneficio:"Pagamento Boleto Bancario"
        }
    ]
    res.render("BeneficioBNDES/bndes.ejs", {
        Empresa: Empresa,
        Beneficio: Beneficio,
        BeneficioBNDES: BeneficioBNDES
    });
})
app.post("/BeneficioATM", (req, res)=>{
    var TransATM = req.body.TransATM;
    var NumeroDocumento = req.body.NumeroDocumento;
    var Beneficiario = req.body.Beneficiario;
    var Telefone = req.body.Telefone;
    var CPF = req.body.CPF;
    var CNPJ = req.body.CNPJ;
    var Aditamento = req.body.Aditamento;
    var Empresa = req.body.Empresa;
    var Nativo = req.body.Nativo;
    var email = req.body.email;
    var email2 = req.body.email2;
    var ATM = req.body.ATM;
    var Banco = req.body.Banco;
    var Agencia = req.body.Agencia;
    var ContaCorrente = req.body.ContaCorrente;
    var Motivo = req.body.Motivo;
    var valor = req.body.valor;
    res.send("Transaçao ATM, <br> TransATM : "+TransATM+" "+" Numero Documento : "+NumeroDocumento
        +"<br>"+" Beneficiario : "+Beneficiario+" "+" Fone : "+Telefone+"<br>"
        +" Pessoa Fisica : CPF : "+CPF+"<br>"+" Pessoa Juridica CNPJ: "+CNPJ+"<br>"
        +"Aditamento : "+Aditamento+"<br>"+"Empresa : "+Empresa+"<br>"+"Nativo : "+Nativo+" <br> "
        +"e-mail : "+email+"<br>"+"e-mail : "+email2+"<br>"+" Check in Online : ATM "+ATM+"<br>"
        +" Banco Beneficiario "+Banco+" "+"Agencia: "+Agencia+" "+"Conta: "+ContaCorrente+"<br>"
        +"Motivo Ref: "+Motivo+"<br>"+" Valor Transaçao ATM : us dolar :$"+valor);
})
app.post("/CreditoOnline", (req, res)=>{
    var informe = req.body.informe;
    var deposito = req.body.deposito;
    res.send("Deposito efetuado com sucesso <br> informe : "+informe+" <br> "+" deposito: R$ "+ deposito);
    /*CreditoOnlines.create({
        informe: informe,
        deposito: deposito
    }).then(()=>{
        console.log("com sucesso");
       // res.redirect("/");
    });*/
});
app.get("/facebook", (req, res)=>{
    res.render("RedeSociais/facebook.ejs");
})
app.get("/playstore", (req, res)=>{
    const AppGame = req.params.AppGame;
    const Usuario = req.params.Usuario;

    const PlayStoreMicrosofts = [
        {AppGame:"City Sland6", Usuario:"moisesfdl", ID:"6w-84cah", versao:"2.7.2", 
            estrela:true,coin:true,dolar:true, hotmail:true, email:"moisesfdl_pbt@hotmail.com.br",
             CPF:"275.551.158-32", Local:"br", CNPJ:"35.669.326/0001-90",Passaport:"GD743426",Bank:"Itau",
            input:true, value:"brl", BancoItau:true,CreditoEmConta:0.01*60*60*12/12}
    ]
    const PlayStoreGoogles = [
        {AppGame:"Airline Commander", Usuario:"moisesfdl",Qualific:"Primeiro Oficial", DinheiroObtido:true,
            ValorDinheiroObtidoUsDolar:10610000.00,POUSOS:true,DECOLAGENS:true,VOOS_COMPLETOS:true,
            ATIVIDADES_CONCLUIDAS:true,ATIVIDADES_CONCLUIDAS_SEM_FALHAS:true,TOTAL_HORAS_DE_VOO:true,
            DESAFIOS:true,Plataform:"Celular",Celular:"12996497466",email2:"moisesprobabilidade@gmail.com",
            CPF:"275.551.158-32",BancoItau:true,CreditoEmConta:0.01*60*60*12/12
        }
    ]

    res.render("AppGame/PlayStore.ejs", {
        AppGame: AppGame,
        Usuario: Usuario,
        PlayStoreMicrosofts: PlayStoreMicrosofts,
        PlayStoreMicrosoft: PlayStoreMicrosoft,
        PlayStoreGoogles: PlayStoreGoogles
    });
})
app.get("/particular", (req, res)=>{
    res.render("Patrimonio/particular.ejs");
})
app.get("/BankInternacional", (req, res)=>{
    res.render("BankInternacional/BankInternacional.ejs", {
        BankInternacional: BankInternacional
    });
})
app.get("/cnh", (req, res)=>{
    res.render("detran/cnh.ejs");
});
app.get("/mastercard", (req, res)=>{
    res.render("mastercard/mastercard.ejs");
});
app.post("/NetLiquidValid", (req, res)=>{
    var Beneficiario = req.body.Beneficiario;
    var email = req.body.email;
    var CPF = req.body.CPF;
    var CNPJ = req.body.CNPJ;
    var telefone = req.body.telefone;
    var Valor = req.body.Valor;
    var time = req.body.time;
    var Banco = req.body.Banco;
    var Agencia = req.body.Agencia;
    var Conta = req.body.Conta;
    var Assinatura = req.body.Assinatura;
    res.send("<ol> Ordem Recebimento <br> Beneficiario : "+Beneficiario+"<br>"+
        "e-mail : "+email+"<br>"+"CPF : "+CPF+" "+"CNPJ : "+CNPJ+"<br>"+"Telefone : "+telefone
        +"<br>"+" Valor : "+Valor+" Time : "+time+"<br>"+"Banco "+Banco+"<br>"
        +" Agencia: "+Agencia+"<br>"+"Conta: "+Conta+"<br>"+"Assinatura : "+Assinatura);
})
app.post("/BeneficioMasterCard", (req, res)=>{
    var Beneficiario = req.body.Beneficiario;
    var CNPJ = req.body.CNPJ;
    var email = req.body.email;
    var ValorPagar = req.body.ValorPagar;
    var NumeroDocumento = req.body.NumeroDocumento;
    var NumeroBoleto = req.body.NumeroBoleto;
    var time = req.body.time;
    var url = req.body.url;
    var telefone = req.body.telefone;
    var beneficio = req.body.beneficio;
    res.send("Pagamento Efetuado <br> : Beneficiario :"+ Beneficiario + " <br> "+ " CNPJ : " 
        + CNPJ + "<br>" + "e-mail : "+email+"<br>"+"Valor A Pagar R$"+ValorPagar+"<br>"+" Numero Documento : "
        +NumeroDocumento+"<br>"+" Boleto :"+NumeroBoleto+"<br>"+" Data Time : "+time+"<br>"+" Url :"+url
        +"<br>"+" Telefone :"+telefone+"<br>"+" beneficio "+beneficio);
})
app.post("/MensagemEnviada", (req, res)=>{
    var titulo = req.body.titulo;
    var descricao = req.body.descricao;
    res.send("Mensagem Enviada c/ sucesso.. <br> titulo "+ titulo +"<br>"+ " " + " descricao : " + descricao);
   /* metadadoscorrecoe.create({
        titulo: titulo,
        descricao: descricao
    })
    .then(()=>{
        res.redirect("/")
    });*/
});      
/*app.post("/MensagemEnviada", (req, res)=>{
    var titulo = req.body.titulo;
    var descricao = req.body.descricao;
    metadadoscorrecoe.create({
            titulo: titulo,
            descricao: descricao
        })
        .then(()=>{
            res.redirect("/")
        });
});*/
app.get("/BancoDoBrasil", (req, res)=>{
    var Reclamacao = req.params.Reclamacao;
    var RevogacaoCotratual = [
        {Beneficiario:"Moises ferreira de lima",CPF:"275.551.158-32",CELULAR:"12996497466",
            EMAIL:"moisesfdl_pbt@hotmail.com.br",Motivo:"Eu Moises ferreira de lima , Rg: 27.950.938-8"
            +"quero de volta a minha oferta publica , o que acarretou em ma conduta administrativa pela \n"
            +"administraçao do banco do brasil , me colocando em ato de sucursal pra fechamento de conta \n"
            +"por ordem administrativa , pra nao entregar ou devolver o valor em conta em minhas maos .\n"
            +"e foi uma atitude de ma fe publica . "
        }
    ]
    res.render("DadosBancario/BancoDoBrasil.ejs", {
        Reclamacao: Reclamacao,
        RevogacaoCotratual: RevogacaoCotratual,
        BancoDoBrasil: BancoDoBrasil
    });
});
app.get("/livelo", (req, res)=>{
    res.render("DadosBancario/livelo.ejs", {
        PontoAcumulado: PontoAcumulado
    });
})
app.get("/CreditoImobiliario", (req, res)=>{
    res.render("financeiro/CreditoImobiliario.ejs");
})
app.listen(3000, function(error){
    if (error) {
        console.log("error...abrindo..manutençao");
    }else {
        console.log("moises ferreira de lima 27555115832");
    }
})


