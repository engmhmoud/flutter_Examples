
class TestBottomSheetWithSetState extends StatefulWidget {
  @override
  _TestBottomSheetWithSetStateState createState() =>
      _TestBottomSheetWithSetStateState();
}

class _TestBottomSheetWithSetStateState
    extends State<TestBottomSheetWithSetState> {
  String _selectedItem = "People";
  PersistentBottomSheetController _controller;

  final _scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      key: _scaffoldKey,
      body: Center(
          child: RaisedButton(
        child: Text(
          "Show",
        ),
        onPressed: () {
          testBottomSheer();
        },
      )),
    );
  }

  Future testBottomSheer() async {
    _controller = _scaffoldKey.currentState.showBottomSheet((context) {
      return Container(
        color: Color(0xFF737373),
        height: 180,
        child: Container(
          child: _buildBottomNavigationMenu(),
          decoration: BoxDecoration(
            color: Theme.of(context).canvasColor,
            borderRadius: BorderRadius.only(
              topLeft: const Radius.circular(10),
              topRight: const Radius.circular(10),
            ),
          ),
        ),
      );
    });
  }

  Column _buildBottomNavigationMenu() {
    return Column(
      children: <Widget>[
        ListTile(
          leading: Icon(
            Icons.ac_unit,
            color: _selectedItem == "Cooling" ? Colors.red : Colors.green,
          ),
          title: Text('Cooling'),
          onTap: () => _selectItem('Cooling'),
        ),
        ListTile(
          leading: Icon(
            Icons.accessibility_new,
            color: _selectedItem == "People" ? Colors.red : Colors.green,
          ),
          title: Text('People'),
          onTap: () => _selectItem('People'),
        ),
        ListTile(
          leading: Icon(
            Icons.assessment,
            color: _selectedItem == "Stats" ? Colors.red : Colors.green,
          ),
          title: Text('Stats'),
          onTap: () => _selectItem('Stats'),
        ),
      ],
    );
  }

  void _selectItem(String name) {
    print(name);
    setState(() {
      _controller.setState(() {
        _selectedItem = name;
      });
    });
  }
}
