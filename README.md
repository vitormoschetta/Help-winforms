# Help-winforms

## Alertas
```
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.OK, MessageBoxIcon.Information);
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.YesNo, MessageBoxIcon.Question);
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.YesNoCancel, MessageBoxIcon.Warning);
```

```
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.OK, MessageBoxIcon.Information);
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.Ok, MessageBoxIcon.Error);
MessageBox.Show("Mensagem!", "Titulo", MessageBoxButtons.Ok, MessageBoxIcon.Warning);
```

MessageBoxButtons => Opçoes de botões ao usuário.

MessageBoxIcon => Tipo de ícons na mensagem.

## Modal
#### Passar informações de um Form para outro:
###### Form que passa:
```
FrmInclusaoTelefone frmInclusaoTelefone = new FrmInclusaoTelefone(this);
frmInclusaoTelefone.Show();
```

###### Form que recebe (no construtor):
```
public partial class FrmInclusaoTelefone : Form
{
    private string CpfCnpj;
    private string NomeCliente;        
    public FrmInclusaoTelefone(FrmCliente frmCliente)
    {
        InitializeComponent();                        
        CpfCnpj = frmCliente.txtCpfCnpj.Text.ToString();
        NomeCliente = frmCliente.cbCliente.Text.ToString();
    }
}
```

#### Abrir um form filho, e depois que fechar atualizar o form pai:
```
FrmInclusaoTelefone frmInclusaoTelefone = new FrmInclusaoTelefone(this);
frmInclusaoTelefone.ShowDialog();
PopulaGridTelefone(txtCpfCnpj.Text);
```
