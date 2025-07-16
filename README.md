class Trabalhador{
    private Nome: string;
    private Salario: number;
    constructor(nome: string, salario = 3000){
        this.Nome = nome;
        if (salario >= 3000){
            this.Salario = salario;
        }
        else{
            this.Salario = 3000
            console.log("NAO TEM CMO NAO TER 3MIL!!!!!!!!!!!!! aceita bebe rsrsrsrsrsrsrsrsrs🤤")
        }
    }
    getNome(): string{
        return this.Nome;
}
    getSalariooooooooooooooooooooooo(): Number{
        return this.Salario;
    }
    setSalario(S: number){
        if (S >= 3000){
            this.Salario = S
        }
        else{
            this.Salario = 3000
        }
    }
}
class FUncionarioBAncario extends Trabalhador{
    private cpf: number
    constructor(nome:string, salario:number, cpf:number){
    super(nome, salario)
    this.cpf = cpf
    }
    getCPF(): number{
        return this.cpf; //o encapsulamento nesse contexto seria para garantir a segurança do CPF tal como Cadastro de Pessoa Fisica, um numero de grande importancia que necessita ter sua segurança preservada.
}}
class CAixa extends FUncionarioBAncario{}
class FAIXneiro extends FUncionarioBAncario{
    private TUrno: string;
    constructor(nome:string, salario:number, cpf:number, TUrno:string){
        super(nome,salario,cpf)
        if(TUrno== 'MAnhã' || TUrno== 'TArde' || TUrno == 'NOite'){
            this.TUrno = TUrno
        }
        else{
            this.TUrno = 'MAnhã'
                console.log('isso nao eh um TUrno seu lioxo')
        }
    }
    ATualizarTUrno(TUrno:string){
        if(this.TUrno== 'MAnhã' || this.TUrno== 'TArde' || this.TUrno == 'NOite'){
            this.TUrno = TUrno
        }
        else{
                console.log('isso nao eh um TUrno seu lioxo')
        }
    }
}
class GErente extends FUncionarioBAncario{
    private EQuipe: FUncionarioBAncario[] = []
    private BonusSalario: number
    constructor(nome:string, salario:number, cpf:number, BonusSalario = 2000){
        super(nome, salario, cpf)
        this.BonusSalario = BonusSalario
    }
    adicionar(FUNcionario: FUncionarioBAncario){
        this.EQuipe.push(FUNcionario)
  }
  imprimeFUncionario(){
      let mar: number;
      mar = 0 
      let len = this.EQuipe.length
      while (mar < len){
          console.log(this.EQuipe[mar])
          mar++
      }
    }
    getSalariooooooooooooooooooooooo(): number {
        return this.BonusSalario + this.getSalariooooooooooooooooooooooo()
        
    }
}

let lojadecafedaalyne:GErente
lojadecafedaalyne = new GErente('LOjas DE CAfe DA ALyne', 5000000000000000000000, 12345678922)
let videozinhosgab:CAixa
videozinhosgab = new CAixa('VIDEOSZINHOS DO GAB GAMEPLAYS', 3001, 56456123138979)
let desempregojuliaajudou:CAixa
desempregojuliaajudou = new CAixa('JUlia AJudou', 4000,5465897423130887)
let pobrinhosmarcelos:FAIXneiro
pobrinhosmarcelos = new FAIXneiro('PObrinhos MArcelos', 3000, 7987877454123231, 'MAnhã')
let riquinhaslucialuciana:FAIXneiro
riquinhaslucialuciana = new FAIXneiro('RIquinhas LUcia LUciana', 90000, 7215478513213154, 'NOite')
lojadecafedaalyne.adicionar(videozinhosgab)
lojadecafedaalyne.adicionar(desempregojuliaajudou)
lojadecafedaalyne.adicionar(pobrinhosmarcelos)
lojadecafedaalyne.adicionar(riquinhaslucialuciana)
pobrinhosmarcelos.setSalario(3999)
desempregojuliaajudou.setSalario(6000)
videozinhosgab.setSalario(3002)
pobrinhosmarcelos.ATualizarTUrno('TArde')
riquinhaslucialuciana.ATualizarTUrno('MAnhã')

console.log("No dia 29 de fevereiro o gerente deu um aumento para JUlia AJudou pois ela ajudou MUITOTOOO, também houve aumento no salario do outro caixa VIDEOSZINHOS DO GAB GAMEPLAYS ele caixou demiasssssss, há também o aumento salarial da faxineira RIquinhas LUcia LUciana!!! ela faxinou MUTIOOOOOOOOOOOOOO. PObrinhos MArcelos e RIquinhas LUcia LUciana limpam o banco e obtem transferencia de turno!!!!!!!!!!!!")
