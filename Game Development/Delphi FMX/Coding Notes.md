FullScreen := True;
To activate a Fullscreen prompt
----------------------------------------------------------------------------
Fullscreen := false;
To deactivate a Fullscreen prompt
----------------------------------------------------------------------------
Fullscreen := not(Fullscreen);
To toggle between states
----------------------------------------------------------------------------
SectionTutorial.BringToFront;                    example(SectionTutorial)
When needing to switch to different screen when clicking button
----------------------------------------------------------------------------
SectionTutorial.Repaint;                         example(SectionTutorial)
To prevent MouseEntry & MouseLeave from moving the object from its intended position.
----------------------------------------------------------------------------
ShowMessage('Found Tribrachidiun Heraldicum 3!');
-----------------------------------------------------------------------------
Counter counting down from total when items are selected:
      rocedure TFrame_Map1.Loaded;
      begin
        inherited;
        FFound := TStringList.Create;
        FTotal := 40; // total number of logical items
        FRemaining := FTotal;
        UpdateCounter;
      end;
      
      destructor TFrame_Map1.Destroy;
      begin
        FFound.Free;
        inherited;
      end;
      
      procedure TFrame_Map1.UpdateCounter;
      begin
        if Assigned(lbl_Title_Counter) then
          lbl_Title_Counter.Text := Format('%d/%d', [FRemaining, FTotal]);
      end;
      
      function TFrame_Map1.TryFoundItem(const AKey: string): Boolean;
      begin
        // if already found, return false and do nothing
        if (AKey <> '') and (FFound.IndexOf(AKey) >= 0) then
        begin
          Result := False;
          Exit;
        end;
      
        // mark found and decrement
        if AKey <> '' then
          FFound.Add(AKey);
      
        if FRemaining > 0 then
          Dec(FRemaining);
      
        UpdateCounter;
        Result := True;
      end;
      
      procedure TFrame_Map1.Found_Auroralumina_attenboroughii_1(Sender: TObject);
      begin
        if TryFoundItem('Auroralumina_Attenboroughii') then
          ShowMessage('Found Found Auroralumina attenboroughii 1!');
      end;
---------------------------------------------------------------------------------------
